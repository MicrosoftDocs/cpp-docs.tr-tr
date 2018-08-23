---
title: Genel MBCS programlama önerileri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- _mbcs
dev_langs:
- C++
helpviewer_keywords:
- MBCS [C++], dialog box fonts
- MS Shell Dlg
- MBCS [C++], programming
- dialog boxes [C++], fonts
ms.assetid: 7b541235-f3e5-4af0-b2c2-a0112cd5fbfb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0a23ed1283241d3582c0bd548553cb2fed9a47fa
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42596801"
---
# <a name="general-mbcs-programming-advice"></a>Genel MBCS Programlama Önerileri
Aşağıdaki ipuçlarını kullanın:  
  
-   Esneklik için çalışma zamanı makroları kullanın `_tcschr` ve `_tcscpy` mümkün olduğunda. Daha fazla bilgi için [Tchar.h'de genel metin eşlemeleri](../text/generic-text-mappings-in-tchar-h.md).  
  
-   C çalışma zamanı kullanmak `_getmbcp` geçerli kod sayfası hakkında bilgi almak için işlevi.  
  
-   Dize kaynakları yeniden kullanmayın. Hedef dile bağlı olarak, belirli bir dize çevrildiğinde farklı bir anlama sahip olabilir. Örneğin, "File" uygulamanın ana menü "Dosya" iletişim kutusunda bir dizeden farklı şekilde çevrilebilir. Aynı ada sahip birden fazla dize kullanmanız gerekiyorsa, her biri için farklı dize kimliklerini kullanın.  
  
-   Uygulamanızı bir MBCS özellikli işletim sistemi üzerinde mi çalışan bulmak isteyebilirsiniz. Bunu yapmak için program başlangıcında bayrağının ayarlanması; API çağrılarında güvenmeyin.  
  
-   İletişim kutusu tasarlarken, yaklaşık % 30'luk izin MBCS çeviri için statik metin denetimlerin sonunda fazladan boşluk.  
  
-   Bazı yazı tipleri tüm sistemlerine kullanılamadığından, uygulamanıza yazı seçerken dikkatli olun.  
  
-   İletişim kutuları için yazı tipini seçerken kullanmak [MS Shell Dlg](http://msdn.microsoft.com/library/windows/desktop/dd374112) MS tırnaksız veya Helvetica yerine. MS Shell Dlg ile doğru yazı tipi iletişim kutusu oluşturmadan önce sistem tarafından değiştirilir. MS Shell Dlg kullanarak bu yazı tipi ile ilgili işletim sistemindeki değişiklikler otomatik olarak kullanılabilir olmasını sağlar. (Bu sistemlerin MS Shell Dlg doğru şekilde işlememesi çünkü MFC MS Shell Dlg DEFAULT_GUI_FONT veya sistem yazı tipi Windows 95, Windows 98 ve Windows NT 4 ile değiştirir.)  
  
-   Uygulamanızı tasarlarken hangi dizeleri yerelleştirilmiş karar verin. Bu konuda şüpheleriniz varsa herhangi bir dize yerelleştirilmiş olduğunu varsayalım. Bu nedenle, yerelleştirilebilir dize yerelleştirilemeyen karıştırmayın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MBCS programlama ipuçları](../text/mbcs-programming-tips.md)   
 [İşaretçileri Artırma ve Azaltma](../text/incrementing-and-decrementing-pointers.md)