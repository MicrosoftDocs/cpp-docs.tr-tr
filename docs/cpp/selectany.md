---
title: selectany
ms.date: 11/04/2016
f1_keywords:
- selectany_cpp
helpviewer_keywords:
- __declspec keyword [C++], selectany
- selectany __declspec keyword
ms.assetid: 9c353017-5a42-4f50-b741-bd13da1ce84d
ms.openlocfilehash: e8ca82900ffd16264aca494950d4793029e55d9c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365595"
---
# <a name="selectany"></a>selectany

**Microsoft'a Özgü**

Derleyiciye, bildirilen genel veri öğesinin (değişken veya nesne) herhangi bir comdat (paketlenmiş işlev) olduğunu söyler.

## <a name="syntax"></a>Sözdizimi

```
__declspec( selectany ) declarator
```

## <a name="remarks"></a>Açıklamalar

Bağlantı zamanda, bir COMDAT'ın birden çok tanımı görülürse, bağlayıcı birini seçer ve geri kalanını atar. Bağlayıcı seçeneği [/OPT:REF](../build/reference/opt-optimizations.md) (Optimizasyonlar) seçilirse, bağlayıcı çıkışındaki tüm başvurulanamayan veri öğelerini kaldırmak için COMDAT eliminasyonu oluşur.

Bildirimdeki global işlev veya statik yöntemlerle oluşturucular ve atamalar bir referans oluşturmaz ve /OPT:REF ortadan kaldırılmasını engellemez. Bu tür koddan kaynaklanan yan etkiler, verilere başka başvuru bulunmadığında bağlı olmamalıdır.

Dinamik olarak başlatılan, genel nesneler için **selectany,** başvurulmamış bir nesnenin başlatma kodunu da atar.

Genel bir veri öğesi normalde bir EXE veya DLL projesinde yalnızca bir kez baş harfe çevrilebilir. **selectany,** aynı üstbilgi birden fazla kaynak dosyada göründüğünde, üstbilgiler tarafından tanımlanan genel verilerin başlatılmasında kullanılabilir. **selectany** hem C hem de C++ derleyicilerinde kullanılabilir.

> [!NOTE]
> **selectany** yalnızca dışarıdan görünen genel veri öğelerinin gerçek başlatılmasına uygulanabilir.

## <a name="example"></a>Örnek

Bu kod, **selectany** özniteliğinin nasıl kullanılacağını gösterir:

```cpp
//Correct - x1 is initialized and externally visible
__declspec(selectany) int x1=1;

//Incorrect - const is by default static in C++, so
//x2 is not visible externally (This is OK in C, since
//const is not by default static in C)
const __declspec(selectany) int x2 =2;

//Correct - x3 is extern const, so externally visible
extern const __declspec(selectany) int x3=3;

//Correct - x4 is extern const, so it is externally visible
extern const int x4;
const __declspec(selectany) int x4=4;

//Incorrect - __declspec(selectany) is applied to the uninitialized
//declaration of x5
extern __declspec(selectany) int x5;

// OK: dynamic initialization of global object
class X {
public:
X(int i){i++;};
int i;
};

__declspec(selectany) X x(1);
```

## <a name="example"></a>Örnek

Bu kod, [/OPT:ICF](../build/reference/opt-optimizations.md) bağlayıcı seçeneğini de kullandığınızda comdat verilerinin katlandığından emin olmak için **selectany** özniteliğinin nasıl kullanılacağını gösterir. Verilerin **selectany** ile işaretlenerek **const** (salt) bir bölüme yerleştirilmesi gerektiğini unutmayın. Salt okunur bölümünü açıkça belirtmeniz gerekir.

```cpp
// selectany2.cpp
// in the following lines, const marks the variables as read only
__declspec(selectany) extern const int ix = 5;
__declspec(selectany) extern const int jx = 5;
int main() {
   int ij;
   ij = ix + jx;
}
```

**END Microsoft Özel**

## <a name="see-also"></a>Ayrıca bkz.

[__declspec](../cpp/declspec.md)<br/>
[Anahtar sözcükler](../cpp/keywords-cpp.md)
