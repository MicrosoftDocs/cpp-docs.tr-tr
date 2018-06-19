---
title: Hızlandırıcı tuşu özelliği | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Key property
ms.assetid: d1570cd9-b414-4cd6-96bd-47c38281eaca
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e4fc56384d666026f4cc7e21f9d8af9347046fd1
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33857213"
---
# <a name="accelerator-key-property"></a>Hızlandırıcı Tuşu Özelliği
Hızlandırıcı tablosunda anahtar özelliği için yasal girişleri şunlardır:  
  
-   0 ile 255 ondalık biçiminde arasında bir tamsayı. Değer, değer ASCII veya ANSI aşağıdaki gibi değerlendirilir olup olmadığını belirler:  
  
    -   Tek basamaklı sayıları, her zaman ASCII veya ANSI değerleri olarak değil, karşılık gelen anahtar olarak yorumlanır.  
  
    -   Değer 1'den sıfırlarla önlerine 26 olarak yorumlanır ^ A'dan ^ Z alfabedeki tutulan CTRL tuşuna basıldığında ASCII değerini temsil eder.  
  
    -   27-32 değerlerinden her zaman üç basamaklı ondalık değer 032 aracılığıyla 027 olarak yorumlanır.  
  
    -   033 ile 255'den 0'ın öncesinde veya ANSI değerler olarak yorumlandığını olmayan değerleri.  
  
-   Bir tek klavye karakteri. A - Z büyük harf veya sayı 0 - 9 ASCII veya sanal anahtar değerleri olabilir; herhangi bir karakteri yalnızca ASCII olur.  
  
-   A - Z aralığında bir tek klavye karakteri (yalnızca büyük harf), bir şapka (^) öncesinde (örneğin, ^ C). Tutulan CTRL tuşuna basıldığında, bu anahtarın ASCII değerini girer.  
  
    > [!NOTE]
    >  ASCII değeri girerken değiştiricisi özellik seçenekleri sınırlıdır. Yalnızca denetim kullanılabilir kullanmak için ALT tuşunu anahtardır.  
  
-   Tüm geçerli sanal anahtarı tanımlayıcısı. Hızlandırıcı tablosunu açılan anahtar kutusunda standart sanal anahtar tanımlayıcıları listesini içerir.  
  
    > [!TIP]
    >  Hızlandırıcı tuşunu tanımlamak için bir başka yolu olan bir giriş veya Hızlandırıcı tablosunda birden çok giriş sağ tıklayın, seçin **sonraki anahtar yazılan** kısayol menüsünden ve anahtarları veya tuş bileşimlerini klavyede tuşuna basın. **Sonraki anahtar yazılan** komutu edinilebilir de **Düzenle** menüsü.  
  
## <a name="requirements"></a>Gereksinimler  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hızlandırıcı özelliklerini ayarlama](../windows/setting-accelerator-properties.md)   
 [Hızlandırıcı tablosunu düzenleme](../windows/editing-in-an-accelerator-table.md)   
 [Hızlandırıcı Düzenleyicisi](../windows/accelerator-editor.md)