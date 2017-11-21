---
title: "Sembol değeri kısıtlamaları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.editors.symbol.restrictions.value
dev_langs: C++
helpviewer_keywords:
- symbols, value restrictions
- restrictions, symbol values
ms.assetid: 32467ec3-690b-4cd0-a4d0-7d189a3296cb
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9c3edccbf88ea6aeb975b9861ebd80817362c245
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="symbol-value-restrictions"></a>Sembol Değeri Kısıtlamaları
Sembol değeri için normal şekilde ifade tamsayı olabilir # önişlemci yönergeleri define. Sembol değerleri bazı örnekleri şunlardır:  
  
```  
18  
4001  
0x0012  
-3456  
```  
  
 Sembol değerleri kaynaklar (Hızlandırıcıları, bit eşlemler, imleçler, iletişim kutuları, simgeler, menüler, dize tabloları ve sürüm bilgileri) için ondalık sayı 0 ile 32.767 aralığında olması gerekir (ancak onaltılık olamaz). İletişim kutusu denetimleri veya bireysel dizelerini dize tablosunda gibi kaynaklar bölümlerinin sembol değerleri 0 ile 65,534 veya ile 32.767 32,768 olabilir.  
  
 Kaynak semboller 16 bit numaralarıdır. Bunları işaretli veya işaretsiz olarak girebilirsiniz, ancak bunlar dahili olarak imzalanmamış tamsayı olarak kullanılır. Bu nedenle negatif sayılar, karşılık gelen pozitif değerlerine cast.  
  
 Sembol değerleri bazı kısıtlamalar şunlardır:  
  
-   MFC ve Visual Studio geliştirme ortamı bazı aralık sayısı özel amaçlar için kullanın. MFC tarafından numaraların en önemli biti ayarlanmış (-32.768 -1 veya 32.768 için 65,534, oturum bağlı olarak) ile ayrılmıştır.  
  
-   Diğer simge dizeleri kullanarak bir sembol değeri tanımlayamazsınız. Örneğin, aşağıdaki simge tanımını desteklenmiyor:  
  
    ```  
    #define IDC_MYEDIT  IDC_OTHEREDIT  //not supported  
    ```  
  
-   Önişlemci makroları değeri tanımlarla bağımsız değişkenlerle birlikte kullanamazsınız. Örneğin:  
  
    ```  
    #define   IDD_ABOUT  ID(7) //not supported  
    ```  
  
     ne bağımsız olarak geçerli bir ifade değil `ID` için derleme zamanında değerlendirir.  
  
-   Uygulamanızı ifadelerle tanımlanan sembolleri içeren varolan bir dosyanın olabilir. Salt okunur semboller symbols eklemek hakkında daha fazla bilgi için bkz: [kullanarak paylaşılan (salt okunur) veya hesaplanan sembolleri](../windows/including-shared-read-only-or-calculated-symbols.md).  
  
 Aralık sayısı hakkında daha fazla bilgi için bkz: [TN023: standart MFC kaynakları](../mfc/tn023-standard-mfc-resources.md).  
  

  
## <a name="requirements"></a>Gereksinimler  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sembolün sayısal değerini değiştirme](../windows/changing-a-symbol-s-numeric-value.md)   
 [Sembol adı kısıtlamaları](../windows/symbol-name-restrictions.md)   
 [Önceden tanımlanmış sembol kimlikleri](../windows/predefined-symbol-ids.md)