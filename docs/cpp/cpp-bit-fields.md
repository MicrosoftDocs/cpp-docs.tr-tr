---
title: C++ Bit Alanları
ms.date: 11/19/2018
helpviewer_keywords:
- bitfields [C++]
- fields [C++], bit
- bit fields
ms.assetid: 6f4b62e3-cc1d-4e5d-bf34-05904104f71a
ms.openlocfilehash: bba57d495553e9622fcece9d036fc4f6eff3fa04
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75301606"
---
# <a name="c-bit-fields"></a>C++ Bit Alanları

Sınıflar ve yapılar, tamsayı türünden daha az depolama alanı kaplayan üyeler içerebilir. Bu üyeler bit alanları olarak belirtilir. Bit alanı *üyesi-declarator* belirtiminin sözdizimi şöyledir:

## <a name="syntax"></a>Sözdizimi

*bildirimci* **:** *sabit ifadesi*

## <a name="remarks"></a>Açıklamalar

(İsteğe bağlı) *bildirimci* , üyenin programda erişildiği addır. Bu (numaralandırılmış türler dahil) bir tamsayı türü olmalıdır. *Sabit ifade* , üyenin yapıda kapladığı bit sayısını belirtir. Doldurmak için, adsız bit alanları (diğer bir deyişle, hiçbir tanımlayıcısı olmayan bit alanları) kullanılabilir.

> [!NOTE]
> Bir genişlik 0 ' ın adlandırılmamış bir bit alanı, bir sonraki bit alanının bir sonraki **tür** sınırına hizalanmaya zorlar; burada **tür** üyenin türüdür.

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

![Tarih nesnesinin bellek düzeni](../cpp/media/vc38uq1.png "Tarih nesnesinin bellek düzeni") <br/>
Tarih Nesnesinin Bellek Düzeni

`nYear` 8 bit uzunluğunda olduğunu ve belirtilen tür, **işaretsiz** **Short**sözcük sınırını taşıyacağını unutmayın. Bu nedenle, yeni bir **işaretsiz** **Short**başlangıcında başlamış olur. Tüm bit alanlarının temel türün bir nesnesine sığmasına gerek yoktur; yeni depolama birimleri bildirimde istenen bit sayısına göre ayrılır.

**Microsoft 'a özgü**

Yukarıdaki şekilde gösterildiği gibi, bildirilen verilerin bit alanları olarak sıralanması düşük bitten yüksek bite doğrudur.

**SON Microsoft 'a özgü**

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

ardından, bellek düzeni aşağıdaki şekilde gösterilmiştir:

![Sıfır&#45;uzunlukta bit alanı olan tarih nesnesi düzeni](../cpp/media/vc38uq2.png "Sıfır&#45;uzunlukta bit alanı olan tarih nesnesi düzeni") <br/>
Sıfır Uzunluklu Bit Alanı Olan Tarih Nesnesinin Düzeni

Bir bit alanının temel alınan türü, [Yerleşik türler](../cpp/fundamental-types-cpp.md)bölümünde açıklandığı gibi bir integral türü olmalıdır.

`const T&` türündeki bir başvurunun başlatıcısı `T`türünde bir bit alanına başvuran bir lvalue ise, başvuru doğrudan bit alanına bağlanmaz. Bunun yerine, başvuru, bit alanının değerini tutmak için geçici olarak başlatılmış bir öğesine bağlanır.

## <a name="restrictions-on-bit-fields"></a>Bit alanları için kısıtlamalar

Bit alanlarındaki hatalı işlemler aşağıdaki listede görülmektedir:

- Bir bit alanı adresini alma.

- Bir bit alanıyla**const** olmayan bir başvuru başlatılıyor.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar ve Yapılar](../cpp/classes-and-structs-cpp.md)