---
title: selectany
ms.date: 11/04/2016
f1_keywords:
- selectany_cpp
helpviewer_keywords:
- __declspec keyword [C++], selectany
- selectany __declspec keyword
ms.assetid: 9c353017-5a42-4f50-b741-bd13da1ce84d
ms.openlocfilehash: a6bf4076dfecbd29035716285f52c0a9faf81067
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62267303"
---
# <a name="selectany"></a>selectany

**Microsoft'a özgü**

Derleyici, bildirilen genel veri öğesi (değişken veya nesne) (paketlenmiş bir işlev) çekme herhangi COMDAT olduğunu söyler.

## <a name="syntax"></a>Sözdizimi

```
__declspec( selectany ) declarator
```

## <a name="remarks"></a>Açıklamalar

Bağlantı zaman COMDAT birden çok tanımları görülürse bağlayıcı birini seçer ve rest atar. Bağlayıcı seçeneği [/OPT: ref](../build/reference/opt-optimizations.md) (iyileştirmeler) seçildiğinden, bağlayıcı çıkışta tüm başvurulanmamış veriyi öğeleri kaldırmak için COMDAT eleme çıkar.

Oluşturucular ve atama genel işlev veya statik yöntem bildiriminde bir başvuru oluşturmayın ve/OPT: ref eleme önlemez. Diğer başvuru verileri için mevcut olduğunda bu tür kod kaynaklanan yan etkilerin bağımlı değil.

Dinamik olarak başlatılmış, genel nesneler için **selectany** başvurulmayan bir nesnenin başlatma kodu de iptal eder.

Genel veri öğesi genellikle bir EXE veya DLL projesinde yalnızca bir kez başlatılabilir. **selectany** birden fazla kaynak dosyada aynı üst bilgi göründüğünde üstbilgileri tarafından tanımlanan genel veri başlatma içinde kullanılabilir. **selectany** C ve C++ derleyicilerde kullanılabilir.

> [!NOTE]
>  **selectany** yalnızca dışarıdan görünür olan global veri öğeleri gerçek başlatılması için uygulanabilir.

## <a name="example"></a>Örnek

Bu kodu nasıl kullanılacağını gösterir **selectany** özniteliği:

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

Bu kodu nasıl kullanılacağını gösterir **selectany** ayrıca kullandığınızda veri COMDAT katlamasını emin olmak için öznitelik [/OPT: ICF](../build/reference/opt-optimizations.md) bağlayıcı seçeneği. Veri ile işaretlenmelidir Not **selectany** ve yerleştirilmiş bir **const** (salt okunur) bölümü. Salt okunur bölümünde açıkça belirtmeniz gerekir.

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

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__declspec](../cpp/declspec.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)