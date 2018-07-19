---
title: C++ Bit alanları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- bitfields [C++]
- fields [C++], bit
- bit fields
ms.assetid: 6f4b62e3-cc1d-4e5d-bf34-05904104f71a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4dcfd93d1529844c7e5b72d61a6f1fd87d6dd3a7
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37940442"
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

![Bir tarih nesnesinin bellek düzeni](../cpp/media/vc38uq1.png "vc38UQ1") bellek düzeni, tarih nesnesi

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

![Sıfır ile tarih nesnesinin düzeni&#45;uzunluklu bit alanı](../cpp/media/vc38uq2.png "vc38UQ2") sıfır uzunluklu Bit alanı ile tarih nesnesinin düzeni

Bir bit alanının temel türü bölümünde anlatıldığı gibi bir tamsayı türü olmalıdır [temel türler](../cpp/fundamental-types-cpp.md).

Varsa bir başvuru türü için Başlatıcı `const T&` türünün bir bit alanına başvuran bir lvalue değeridir `T`, başvuruyu bit alanı için doğrudan bağlı değil. Bunun yerine, başvuru bit alanının değerini tutmak için başlatılan bir geçici bağlıdır.

## <a name="restrictions-on-bit-fields"></a>Bit alanları kısıtlamaları

Bit alanlarındaki hatalı işlemler aşağıdaki listede görülmektedir:

- Bir bit alanı adresini alma.

- Olmayan bir başlatma**const** bit alanı ile başvuru.

## <a name="see-also"></a>Ayrıca bkz.

- [Sınıflar ve Yapılar](../cpp/classes-and-structs-cpp.md)
