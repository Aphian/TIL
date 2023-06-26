## many_to_many
- N : M의 관계 표현
- class 안의 `ForeignKey`로만으로는 표현이 불가능
- `join table`을 생성 하여 표현
- `models.py` 모델링
  1. `인스턴스 = models.ManyToManyField()`
  2. `through` : `join table`에 컬럼을 추가하기 위한 클래스 참소
  3. `through_fields` : 참조된 클래스에서 사용된 외래키
  4. `related_name` : 역으로 참조 할 경우 명확한 이름으로 하기 위해 사용
  5. ex)
  ```
  class Doctor(models.Model):
    name = models.CharField(max_length=100)

  class Patient(models.Model):
    name = models.CharField(max_length=100)
    # patient 객체 => doctors 로 접근 / 정참조
    doctors = models.ManyToManyField(Doctor, 
                                     through='Reservation', 
                                     through_fields=('patient', 'doctor'),
                                     # Doctor 객체 => 기본값 patient_set
                                     # 역참조 참조 이름 변경
                                     related_name='patients',
                                     )
  class Reservation(models.Model):
    doctor = models.ForeignKey(Doctor, on_delete=models.CASCADE, related_name='reservations')
    patient = models.ForeignKey(Patient, on_delete=models.CASCADE, related_name='reservations')
    date = models.DateField()
  
  ```
### 모델링
- `ERDcloud` 활용
- `ERD` 작업시 컬럼명만으로 하는데, 컬럼명에 실제데이터도 같이 넣으면서 하면 보다 머리속으로 생각하면서 하는것 보다 명확히 눈에 보여 효율적으로 모델링 가능하다.