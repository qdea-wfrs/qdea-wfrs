import numpy as np
import matplotlib.pyplot as plt

np.random.seed(1)  # 재현성을 위해 시드 설정

# 평균, 최고점, 분산 설정
mean = 25.98
max_score = 77
variance = 20

# 데이터 생성
data = np.random.normal(mean, np.sqrt(variance), 1000)
data[data > max_score] = max_score  # 최고점 이상의 값은 최고점으로 제한

# 히스토그램 그리기
plt.hist(data, bins=30, density=True, alpha=0.7, color='skyblue')

# 분산 값 표시
plt.text(0.7, 0.8, '평균 = 25.98\n최고점 = 77\n분산 = 20', transform=plt.gca().transAxes, fontsize=10)

plt.xlabel('점수')
plt.ylabel('밀도')
plt.title('시험 점수 분포')
plt.show()
