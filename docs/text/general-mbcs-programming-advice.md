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
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ab2b67c82a04a0c355761ec6572a9718d03c4666
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33855805"
---
# <a name="general-mbcs-programming-advice"></a>Genel MBCS Programlama Önerileri
Aşağıdaki ipuçlarını kullanın:  
  
-   Esneklik için çalışma zamanı makrolar gibi kullandığınız `_tcschr` ve `_tcscpy` mümkün olduğunda. Daha fazla bilgi için bkz: [Tchar.h'de genel metin eşlemeleri](../text/generic-text-mappings-in-tchar-h.md).  
  
-   C çalışma zamanı kullanmak `_getmbcp` geçerli kod sayfası hakkında bilgi almak için işlevi.  
  
-   Dize kaynakları yeniden kullanma. Hedef Dil bağlı olarak verilen bir dize çevrildiğinde farklı bir anlama sahip olabilir. Örneğin, "Dosyası" uygulamanın ana menü farklı iletişim kutusunda "dosyası" dizesinden çevir. Aynı ada sahip birden çok dize kullanmanız gerekiyorsa, her biri için farklı bir dize kimlikleri kullanın.  
  
-   Uygulamanızı MBCS etkinleştirilmiş bir işletim sisteminde olup çalıştıran bulmak isteyebilirsiniz. Bunu yapmak için program başlangıcında bir bayrak ayarlayın; API çağrılarına güvenmeyin.  
  
-   İletişim kutuları tasarlarken, yaklaşık olarak %30 izin MBCS çevirisi için statik metin denetimleri sonunda boşluk.  
  
-   Bazı yazı tipleri tüm sistemlerde kullanılabilir olmadığından, uygulamanız için yazı tipi seçerken dikkatli olun.  
  
-   İletişim kutuları için yazı tipi seçerken, kullanmak [MS Kabuk iletişim kutusu](http://msdn.microsoft.com/library/windows/desktop/dd374112) MS Sans Serif veya Helvetica yerine. MS Kabuk iletişim kutusu ile doğru yazı tipi iletişim kutusu oluşturmadan önce sistem tarafından değiştirilir. MS Kabuk iletişim kutusu kullanılarak bu yazı tipi ile mücadele etmek için işletim sisteminde değişiklikleri otomatik olarak kullanılabilir olmasını sağlar. (Bu sistemleri MS Kabuk iletişim kutusu doğru şekilde işlemez çünkü MFC MS Kabuk iletişim kutusu DEFAULT_GUI_FONT veya sistem yazı tipi Windows 95, Windows 98 ve Windows NT 4 ile değiştirir.)  
  
-   Uygulamanızı tasarlarken hangi dizeleri yerelleştirilmiş karar verin. Emin değilseniz, verilen herhangi bir dize yerelleştirilmiş olduğunu varsayalım. Bu nedenle, yerelleştirilebilir dizeler yerelleştirilemeyen karışık kullanmayın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MBCS programlama ipuçları](../text/mbcs-programming-tips.md)   
 [İşaretçileri Artırma ve Azaltma](../text/incrementing-and-decrementing-pointers.md)