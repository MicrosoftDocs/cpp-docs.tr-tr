---
title: section
ms.date: 11/04/2016
f1_keywords:
- section_CPP
- vc-pragma.section
helpviewer_keywords:
- pragmas, section
- section pragma
ms.assetid: c67215e9-2c4a-4b0f-b691-2414d2e2d96f
ms.openlocfilehash: 41479d7d8767438d0e59fbe6beb7e435459dcb1b
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59023249"
---
# <a name="section"></a>section

Bir .obj dosyasında bölüm oluşturur.

## <a name="syntax"></a>Sözdizimi

```
#pragma section( "section-name" [, attributes] )
```

## <a name="remarks"></a>Açıklamalar

Koşulları anlamını *segment* ve *bölümü* bu konudaki birbirinin yerine kullanılabilir.

Bir bölüm tanımlandıktan sonra derleme geri kalanı için geçerli kalır. Ancak, kullanmalısınız [__declspec(allocate)](../cpp/allocate.md) veya hiçbir şey bölümünde yer alır.

*Bölüm adı* bölümün adı gerekli bir parametredir. Adı herhangi bir standart bölüm adı ile çakışmaması gerekir. Bkz: [/SECTION](../build/reference/section-specify-section-attributes.md) kullanmamanız bölüm oluştururken adları listesi.

*öznitelikleri* bölümüne atamak istediğiniz bir veya daha fazla virgülle ayrılmış özniteliklerin oluşan isteğe bağlı bir parametre. Olası *öznitelikleri* şunlardır:

|Öznitelik|Açıklama|
|-|-|
|**read**|Verileri okuma işlemleri sağlar.|
|**write**|Veri yazma işlemleri sağlar.|
|**Yürütme**|Yürütülecek kodu sağlar.|
|**shared**|Resmi yüklemek tüm işlemler arasında bölümü paylaşır.|
|**nopage**|Bölüm alınabilir değil olarak işaretler; Win32 aygıt sürücülerini yönetmek için kullanışlıdır.|
|**NoCache**|Bölüm önbelleğe alınabilir değil olarak işaretler; Win32 aygıt sürücülerini yönetmek için kullanışlıdır.|
|**Atma**|Bölüm discardable olarak işaretler; Win32 aygıt sürücülerini yönetmek için kullanışlıdır.|
|**remove**|Bölüm değil bellekte olarak işaretler; Sanal cihaz sürücüleri (V*x*D) yalnızca.|

Öznitelikleri belirtmezseniz, bölümü okuyun ve yazma öznitelikleri.

## <a name="example"></a>Örnek

Aşağıdaki örnekte, ilk yönergesinin bölümü ve özniteliklerini tanımlar. Tamsayı `j` içine yerleştirin değil `mysec` ile bildirilmedi çünkü `__declspec(allocate)`; `j` veri bölüme gider. Tamsayı `i` kısımlarda `mysec` sonucu olarak, `__declspec(allocate)` depolama sınıfı özniteliği.

```cpp
// pragma_section.cpp
#pragma section("mysec",read,write)
int j = 0;

__declspec(allocate("mysec"))
int i = 0;

int main(){}
```

## <a name="see-also"></a>Ayrıca bkz.

[Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)