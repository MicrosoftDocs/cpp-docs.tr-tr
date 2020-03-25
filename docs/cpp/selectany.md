---
title: selectany
ms.date: 11/04/2016
f1_keywords:
- selectany_cpp
helpviewer_keywords:
- __declspec keyword [C++], selectany
- selectany __declspec keyword
ms.assetid: 9c353017-5a42-4f50-b741-bd13da1ce84d
ms.openlocfilehash: 38346e41c1e943e9bfda70668a163c630a0b9599
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80178879"
---
# <a name="selectany"></a>selectany

**Microsoft 'a özgü**

Derleyiciye, belirtilen genel veri öğesinin (değişken veya nesne) bir seçim-any COMDAT (paketlenmiş bir işlev) olduğunu söyler.

## <a name="syntax"></a>Sözdizimi

```
__declspec( selectany ) declarator
```

## <a name="remarks"></a>Açıklamalar

Bağlantı zamanında, bir COMDAT 'ın birden fazla tanımı görülebilecekse, bağlayıcı bir tane seçer ve geri kalanını atar. [/OPT: ref](../build/reference/opt-optimizations.md) (geri iyileştirmeler) bağlayıcı seçeneği işaretliyse, bağlayıcı çıkışındaki tüm başvurulmayan veri öğelerini kaldırmak için COMDAT eleme oluşur.

Genel işlev veya bildirimdeki statik yöntemler tarafından oluşturucular ve atama bir başvuru oluşturmaz ve/OPT: REF eleme işlemini engellemez. Bu tür koddan yan etkileri, verilere yönelik başka bir başvuru yoksa bağımlı olmamalıdır.

Dinamik olarak başlatılmış, genel nesneler, **selectany** , başvurulmayan nesnenin başlatma kodunu da atar.

Genel veri öğesi, normalde bir EXE veya DLL projesinde yalnızca bir kez başlatılabilir. **selectany** , aynı üst bilgi birden fazla kaynak dosyasında göründüğünde üstbilgiler tarafından tanımlanan genel verileri başlatırken kullanılabilir. **selectany** , hem C hem C++ de derleyicilerde kullanılabilir.

> [!NOTE]
>  **selectany** yalnızca dışarıdan görünen genel veri öğelerinin gerçek başlatmasına uygulanabilir.

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

Bu kod, [/OPT: ICF](../build/reference/opt-optimizations.md) bağlayıcı seçeneğini de kullandığınızda veri COMDAT katlamasını sağlamak için **selectany** özniteliğini nasıl kullanacağınızı gösterir. Verilerin **selectany** ile işaretlenmiş ve **const** (ReadOnly) bölümüne yerleştirilmiş olması gerektiğini unutmayın. Salt okunurdur bölümünü açıkça belirtmeniz gerekir.

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

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__declspec](../cpp/declspec.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)
