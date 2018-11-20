---
title: C++ Bit Alanları
ms.date: 11/19/2018
helpviewer_keywords:
- bitfields [C++]
- fields [C++], bit
- bit fields
ms.assetid: 6f4b62e3-cc1d-4e5d-bf34-05904104f71a
ms.openlocfilehash: 747920378472cc091928a080e303a0543e287aaa
ms.sourcegitcommit: 9e891eb17b73d98f9086d9d4bfe9ca50415d9a37
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52175099"
---
# <a name="c-bit-fields"></a>C++ Bit Alanları

Sınıflar ve yapılar, tamsayı türünden daha az depolama alanı kaplayan üyeler içerebilir. Bu üyeler bit alanları olarak belirtilir. Bit alanı sözdizimi *üye-Bildiricisi* belirtimi aşağıdadır:

## <a name="syntax"></a>Sözdizimi

*bildirimci* **:** *sabit-ifade*

## <a name="remarks"></a>Açıklamalar

(İsteğe bağlı) *bildirimci* tarafından erişilen üyenin programda adıdır. Bu (numaralandırılmış türler dahil) bir tamsayı türü olmalıdır. *Sabit-ifade* yapı üyesi kapladığı yerin bit sayısını belirtir. Doldurmak için, adsız bit alanları (diğer bir deyişle, hiçbir tanımlayıcısı olmayan bit alanları) kullanılabilir.

> [!NOTE]
> Adlandırılmamış bir bit alanı genişliği 0'ın sonraki sıradaki bit alanını hizalamasını zorlar **türü** sınır, burada **türü** üyenin türüdür.

Aşağıdaki örnek bit alanlarını içeren bir yapıyı bildirir:

```cpp
// bit_fields1.cpp
// compile with: /LD
struct Date {
   unsigned short nWeekDay  : 3;    // 0..7   (3 bits)
   unsigned short nMonthDay : 6;    // 0..31  (6 bits)
   unsigned short nMonth    : 5;    // 0..12  (5 bits)
   unsigned short nYear     : 8;    // 0..100 (8 bits)
};
```

`Date` türünde bir nesnenin kavramsal bellek düzeni aşağıdaki çizimde gösterilmiştir.

![Bir tarih nesnesinin bellek düzeni](../cpp/media/vc38uq1.png "tarih nesnesinin bellek düzeni") <br/>
Tarih Nesnesinin Bellek Düzeni

Unutmayın `nYear` 8 bit uzunluğunda olduğunu ve sözcük sınırının türü bildirilen taşma oluşturursunuz **işaretsiz** **kısa**. Bu nedenle, yeni bir başında başlamış **işaretsiz** **kısa**. Tüm bit alanlarının temel türün bir nesnesine sığmasına gerek yoktur; yeni depolama birimleri bildirimde istenen bit sayısına göre ayrılır.

**Microsoft'a özgü**

Yukarıdaki şekilde gösterildiği gibi, bildirilen verilerin bit alanları olarak sıralanması düşük bitten yüksek bite doğrudur.

**END Microsoft özgü**

Böyle bir yapının bildirimi, aşağıdaki örnekte gösterildiği gibi uzunluğu 0 olan adlandırılmamış bir alanı içeriyorsa,

```cpp
// bit_fields2.cpp
// compile with: /LD
struct Date {
   unsigned nWeekDay  : 3;    // 0..7   (3 bits)
   unsigned nMonthDay : 6;    // 0..31  (6 bits)
   unsigned           : 0;    // Force alignment to next boundary.
   unsigned nMonth    : 5;    // 0..12  (5 bits)
   unsigned nYear     : 8;    // 0..100 (8 bits)
};
```

bellek düzeni aşağıdaki şekilde gösterildiği gibi ise:

![Sıfır ile tarih nesnesinin düzeni&#45;uzunluklu bit alanı](../cpp/media/vc38uq2.png "tarihi Düzen nesnesi sıfır&#45;uzunluklu bit alanı") <br/>
Sıfır Uzunluklu Bit Alanı Olan Tarih Nesnesinin Düzeni

Bir bit alanının temel türü bölümünde anlatıldığı gibi bir tamsayı türü olmalıdır [temel türler](../cpp/fundamental-types-cpp.md).

Varsa bir başvuru türü için Başlatıcı `const T&` türünün bir bit alanına başvuran bir lvalue değeridir `T`, başvuruyu bit alanı için doğrudan bağlı değil. Bunun yerine, başvuru bit alanının değerini tutmak için başlatılan bir geçici bağlıdır.

## <a name="restrictions-on-bit-fields"></a>Bit alanları kısıtlamaları

Bit alanlarındaki hatalı işlemler aşağıdaki listede görülmektedir:

- Bir bit alanı adresini alma.

- Olmayan bir başlatma**const** bit alanı ile başvuru.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar ve Yapılar](../cpp/classes-and-structs-cpp.md)