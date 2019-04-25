---
title: İmzalı Tam Sayı Türlerinden Dönüştürmeler
ms.date: 11/04/2016
helpviewer_keywords:
- integral conversions, from signed
- integers, converting
- conversions [C++], integral
- data type conversion [C++], signed and unsigned integers
- type conversion [C++], signed and unsigned integers
ms.assetid: 5eea32f8-8b14-413d-acac-c063b3d118d7
ms.openlocfilehash: 4d2f0ab43adf3cbad3d1ffa244551c67883c6606
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62312459"
---
# <a name="conversions-from-signed-integral-types"></a>İmzalı Tam Sayı Türlerinden Dönüştürmeler

İmzalı bir tamsayı değerine eşit veya daha büyük boyutta bir işaretsiz tamsayı dönüştürülür ve işaretli tam sayı değeri negatif olmadığında değeri değiştirilmez. Dönüştürme, işaret işaretli tamsayı genişletme tarafından yapılır. İmzalı bir tamsayı, yüksek sıra bitleri kesilip daha kısa işaretli bir tamsayıya dönüştürülür. Sonuç, işaretsiz bir değer olarak, bu örnekte gösterildiği gibi yorumlanır.

```C
int i = -3;
unsigned short u;

u = i;
printf_s( "%hu\n", u );  // Prints 65533
```

İmzalı bir tamsayı, kayan bir değere dönüştürüldüğünde bazı duyarlık ne zaman kaybolabilir dışında hiçbir bilgi kayıp bir **long int** veya **imzasız long int** değerinin bir **float** değeri.

İmzalı tam sayı türlerinden dönüştürmeler aşağıdaki tabloda özetlenmiştir. Bu tabloda varsayar **char** türü varsayılan olarak işaretli. İçin varsayılan değeri değiştirmek için bir derleme zamanı seçeneğini kullanırsanız **char** türü imzalanmamış için verilen dönüştürmeler [işaretsiz tam sayı türlerinden dönüştürmeler](../c-language/conversions-from-unsigned-integral-types.md) için tablo **işaretsiz karakter**  türü geçerli dönüşümler aşağıdaki tabloda, imzalı tam sayı türlerinden dönüştürmeler yerine.

### <a name="conversions-from-signed-integral-types"></a>İmzalı Tam Sayı Türlerinden Dönüştürmeler

|Başlangıç|Bitiş|Yöntem|
|----------|--------|------------|
|**char**1|**short**|Oturum genişletme|
|**char**|**long**|Oturum genişletme|
|**char**|**İmzasız char**|Düzeni korumak; yüksek sıralı bitten işlevi imza biti kaybeder.|
|**char**|**İmzasız short**|Oturum-genişletmek için **kısa**; dönüştürme **kısa** için **işaretsiz**|
|**char**|**İmzasız long**|Oturum-genişletmek için **uzun**; dönüştürme **uzun** için **işaretsiz uzun**|
|**char**|**float**|Oturum-genişletmek için **uzun**; dönüştürme **uzun** için **float**|
|**char**|**double**|Oturum-genişletmek için **uzun**; dönüştürme **uzun** için **çift**|
|**char**|**uzun çift**|Oturum-genişletmek için **uzun**; dönüştürme **uzun** için **çift**|
|**short**|**char**|Düşük düzey baytı korur|
|**short**|**long**|Oturum genişletme|
|**short**|**İmzasız char**|Düşük düzey baytı korur|
|**short**|**İmzasız short**|Bit deseni korumak; yüksek sıralı bitten işlevi imza biti kaybeder.|
|**short**|**İmzasız long**|Oturum-genişletmek için **uzun**; dönüştürme **uzun** için **işaretsiz uzun**|
|**short**|**float**|Oturum-genişletmek için **uzun**; dönüştürme **uzun** için **float**|
|**short**|**double**|Oturum-genişletmek için **uzun**; dönüştürme **uzun** için **çift**|
|**short**|**uzun çift**|Oturum-genişletmek için **uzun**; dönüştürme **uzun** için **çift**|
|**long**|**char**|Düşük düzey baytı korur|
|**long**|**short**|Düşük düzey word koru|
|**long**|**İmzasız char**|Düşük düzey baytı korur|
|**long**|**İmzasız short**|Düşük düzey word koru|
|**long**|**İmzasız long**|Bit deseni korumak; yüksek sıralı bitten işlevi imza biti kaybeder.|
|**long**|**float**|Olarak temsil eden **float**. Varsa **uzun** olamaz tam olarak temsil edilen bazı duyarlık kaybı.|
|**long**|**double**|Olarak temsil eden **çift**. Varsa **uzun** tam olarak temsil edilemez bir **çift**, bazı duyarlık kaybolur.|
|**long**|**uzun çift**|Olarak temsil eden **çift**. Varsa **uzun** tam olarak temsil edilemez bir **çift**, bazı duyarlık kaybolur.|

1. Tüm **char** girişleri varsayar **char** türü varsayılan olarak işaretli.

**Microsoft'a özgü**

Microsoft 32-bit C derleyicisi için bir tamsayı değerine eşdeğer olan bir **uzun**. Dönüştürme bir **int** değeri aynı geçer bir **uzun**.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Atama Dönüştürmeleri](../c-language/assignment-conversions.md)
