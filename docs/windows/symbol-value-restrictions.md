---
title: Sembol değeri kısıtlamaları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.symbol.restrictions.value
dev_langs:
- C++
helpviewer_keywords:
- symbols [C++], value restrictions
- restrictions, symbol values
ms.assetid: 32467ec3-690b-4cd0-a4d0-7d189a3296cb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6b174e46df7822ddf5ffbc747d0a7eb3cd71245e
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44315411"
---
# <a name="symbol-value-restrictions"></a>Sembol Değeri Kısıtlamaları

Sembol değeri için normal şekilde ifade edilen herhangi bir tamsayı olabilir # önişlemci yönergeleri define. Sembol değerlerinin bazı örnekleri aşağıda verilmiştir:

```
18
4001
0x0012
-3456
```

Kaynaklar (Hızlandırıcıları, bit eşlemler, işaretçiler, iletişim kutuları, simgeler, menüler, dize tabloları ve sürüm bilgileri) için Sembol değerlerini ondalık sayı 0 ile 32.767 aralığında olmalıdır (ancak onaltılık olamaz). İletişim kutusu denetimleri veya dize tablosunda, tek tek dizeler gibi kaynaklar bölümleri için Sembol değerlerini 65,534 0 veya -32.768 ile 32.767 olabilir.

Kaynak sembolleri 16 bit sayılardır. Bunları işaretli veya işaretsiz girebilirsiniz, ancak bunlar dahili olarak işaretsiz tamsayılar kullanılır. Bu nedenle negatif sayılar, karşılık gelen pozitif değerlerine dönüştürme.

Sembol değerlerinin bazı kısıtlamalar şunlardır:

- Visual Studio geliştirme ortamını ve MFC bazı aralık sayısı, özel amaçlar için kullanın. MFC tarafından tüm sayılar en anlamlı biti ayarlanmış (-32.768 -1 veya 32.768 için 65,534, oturum bağlı olarak) ile ayrılmıştır.

- Diğer sembol dizeleri kullanan bir sembol değer tanımlayamazsınız. Örneğin, aşağıdaki simge tanımı desteklenmez:

    ```cpp
    #define IDC_MYEDIT  IDC_OTHEREDIT  //not supported
    ```

- Önişlemci makroları değer tanımlarla bağımsız değişkenlerle birlikte kullanamazsınız. Örneğin:

    ```cpp
    #define   IDD_ABOUT  ID(7) //not supported
    ```

   ne bağımsız olarak geçerli bir ifade değil `ID` derleme zamanında değerlendirilir.

- Uygulamanızın ifadeleri ile tanımlanan sembolleri içeren mevcut bir dosya olabilir. Salt okunur semboller symbols ekleme hakkında daha fazla bilgi için bkz. [kullanılarak paylaşılan (salt okunur) veya hesaplanan sembolleri](../windows/including-shared-read-only-or-calculated-symbols.md).

Aralık sayısı hakkında daha fazla bilgi için bkz. [TN023: standart MFC kaynakları](../mfc/tn023-standard-mfc-resources.md).

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[Sembolün Sayısal Değerini Değiştirme](../windows/changing-a-symbol-s-numeric-value.md)  
[Sembol Adı Kısıtlamaları](../windows/symbol-name-restrictions.md)  
[Önceden Tanımlanmış Sembol Kimlikleri](../windows/predefined-symbol-ids.md)