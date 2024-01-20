# 소개
MeshCombineder
유니티 내부에서 메쉬를 합치기 위한 스크립트

### ⚙️ 개발 환경
- Unity 2022.3.3f1
- Visual Studio 2022

## 📌 주요 기능 설명
![image](https://github.com/ImKrap/MeshCombineder/assets/157236702/52d87224-3244-45e0-ae7f-96cb5186bf03)

---

1. MergeSameKeywordMaterial
- 해당 스크립트가 존재하는 오브젝트의 자식들을 머티리얼의 키워드 별로 분류
- 분류된 머티리얼별의 종류에 따라 빈 자식오브젝트로 생성함[자식오브젝트를 부모 오브젝트의 레이어를 따라감]
  ![image](https://github.com/ImKrap/MeshCombineder/assets/157236702/9225f18b-cc31-4bb1-9861-89857f2924fe)

##### ! 해당 기능이 작동 후 자식 오브젝트들은 자동으로 비활성화된 후 Asset/Meshes에 병합된 Mesh가 생성됨

2. ShowOnlyChildCollider
- 자식 오브젝트들의 MeshRenderer를 비활성화하여 Collider만 남겨둔다.

3. ShowChild
- 자식 오브젝트의 MeshRenderer를 활성화와 함께 게임오브젝트도 활성화한다.

4. HideChild
- 자식 오브젝트의 SetActive = False

5. ClearResultOfCombine
- Combineded Objects에 생성된 게임오브젝트를 제거
##### ! 생성된 메쉬는 직접 삭제해야 됨

6. Add~~Collider
- 1번으로 생성된 오브젝트에 컬라이더가 단순히 추가됨

---

## 추천 순서

##### ● 메쉬 병합 시
1. 병합시킬 오브젝트의 상위 오브젝트에 해당 스크립트 추가
2. MeshCollider Name에 이름 지정
3. MergeSameKeywordMaterial를 눌러 활성
4. Asset/Meshes에 생성된 메쉬들을 하위에 생성된 빈 오브젝트 MeshFilter에 차례대로 드래그앤 드롭
5. ShowOnlyChild Collider 클릭[컬라이더가 필요한 경우]
### 같은 키워드로 묶인 머티리얼과 그에 따른 메쉬 지정 후 모습
![image](https://github.com/ImKrap/MeshCombineder/assets/157236702/75a0ab17-0aad-47a6-8d60-68f26e9a1fc2)



##### ● 생성된 메쉬 삭제 시
1. Asset/Meshes에 병합되어 생성된 Mesh를 삭제
2. ClearResultOfCombine 클릭하여 하위에 생성된 오브젝트 제거
3. ShowChild로 오브젝트 활성화
