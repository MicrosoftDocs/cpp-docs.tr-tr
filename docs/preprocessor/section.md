---
description: pragmaMicrosoft C/C++ içindeki bölüm yönergesi hakkında daha fazla bilgi edinin
title: kısmı pragma
ms.date: 01/22/2021
f1_keywords:
- section_CPP
- vc-pragma.section
helpviewer_keywords:
- pragma, section
- section pragma
no-loc:
- pragma
ms.openlocfilehash: 8bd55bbba65480b7345376059489d8aef945ab34
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713239"
---
# <a name="section-no-locpragma"></a>`section` pragma

OBJ dosyasında bir bölüm oluşturur.

## <a name="syntax"></a>Syntax

> **`#pragma section( "`***bölüm-adı* **`"`** [ **`,`** *öznitelikler* ]**`)`**

## <a name="remarks"></a>Açıklamalar

Koşullar *segmenti* ve *bölümü* Bu makalede aynı anlama sahiptir.

Bir bölüm tanımlandıktan sonra, derlemenin geri kalanı için geçerli kalır. Ancak, [`__declspec(allocate)`](../cpp/allocate.md) bölümüne veya bölümüne hiçbir şey yerleştirmeli.

*bölüm adı* , bölümün adı haline gelen gerekli bir parametredir. Ad hiçbir standart bölüm adıyla çakışmamalıdır. [`/SECTION`](../build/reference/section-specify-section-attributes.md)Bir bölüm oluştururken kullanmamanız gereki adların listesi için bkz..

*öznitelikler* , bölüme atanacak bir veya daha fazla virgülle ayrılmış özniteliği içeren isteğe bağlı bir parametredir. Olası *öznitelikler* şunlardır:

| Öznitelik | Açıklama |
|--|--|
| **`read`** | Verilerde okuma işlemlerine izin verir. |
| **`write`** | Veriler üzerinde yazma işlemlerine izin verir. |
| **`execute`** | Kodun yürütülmesini sağlar. |
| **`shared`** | , Görüntüyü yükleyen tüm süreçler arasında bölümü paylaşır. |
| **`nopage`** | Bölümü disk belleğine değil olarak işaretler. Win32 cihaz sürücüleri için faydalıdır. |
| **`nocache`** | Bölümü önbelleklenebilir olarak işaretler. Win32 cihaz sürücüleri için faydalıdır. |
| **`discard`** | Bölümü discardable olarak işaretler. Win32 cihaz sürücüleri için faydalıdır. |
| **`remove`** | Bölümü bellekte yerleşik değil olarak işaretler. Yalnızca sanal aygıt sürücüleri (V *x* D) için. |

Herhangi bir öznitelik belirtmezseniz, bölümü **`read`** ve **`write`** öznitelikleri vardır.

## <a name="example"></a>Örnek

Bu örnekte, ilk bölüm pragma bölümü ve özniteliklerini tanımlar. Tamsayı, `j` `mysec` kullanılarak bildirilmemiş olduğundan içine yerleştirmedi `__declspec(allocate)` . Bunun yerine, `j` veri bölümüne gider. Tamsayı, `i` `mysec` depolama sınıfı özniteliği nedeniyle öğesine gider `__declspec(allocate)` .

```cpp
// pragma_section.cpp
#pragma section("mysec",read,write)
int j = 0;

__declspec(allocate("mysec"))
int i = 0;

int main(){}
```

## <a name="see-also"></a>Ayrıca bkz.

[Pragma yönergeleri ve `__pragma` ve `_Pragma` anahtar sözcükleri](./pragma-directives-and-the-pragma-keyword.md)
