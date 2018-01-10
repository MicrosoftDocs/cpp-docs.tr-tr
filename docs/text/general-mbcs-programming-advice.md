---
title: "Genel MBCS programlama önerileri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: _mbcs
dev_langs: C++
helpviewer_keywords:
- MBCS [C++], dialog box fonts
- MS Shell Dlg
- MBCS [C++], programming
- dialog boxes [C++], fonts
ms.assetid: 7b541235-f3e5-4af0-b2c2-a0112cd5fbfb
caps.latest.revision: "9"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8a09bfb9b30e279e8d0b7696055c1e54ac56bfae
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="general-mbcs-programming-advice"></a>Genel MBCS Programlama Önerileri
Aşağıdaki ipuçlarını kullanın:  
  
-   Esneklik için çalışma zamanı makrolar gibi kullandığınız `_tcschr` ve `_tcscpy` mümkün olduğunda. Daha fazla bilgi için bkz: [Tchar.h'de genel metin eşlemeleri](../text/generic-text-mappings-in-tchar-h.md).  
  
-   C çalışma zamanı kullanmak `_getmbcp` geçerli kod sayfası hakkında bilgi almak için işlevi.  
  
-   Dize kaynakları yeniden kullanma. Hedef Dil bağlı olarak verilen bir dize çevrildiğinde farklı bir anlama sahip olabilir. Örneğin, "Dosyası" uygulamanın ana menü farklı iletişim kutusunda "dosyası" dizesinden çevir. Aynı ada sahip birden çok dize kullanmanız gerekiyorsa, her biri için farklı bir dize kimlikleri kullanın.  
  
-   Uygulamanızı MBCS etkinleştirilmiş bir işletim sisteminde olup çalıştıran bulmak isteyebilirsiniz. Bunu yapmak için program başlangıcında bir bayrak ayarlayın; API çağrılarına güvenmeyin.  
  
-   İletişim kutuları tasarlarken, yaklaşık olarak %30 izin MBCS çevirisi için statik metin denetimleri sonunda boşluk.  
  
-   Bazı yazı tipleri tüm sistemlerde kullanılabilir olmadığından, uygulamanız için yazı tipi seçerken dikkatli olun. Örneğin, Windows 2000 Japonca sürümü Helvetica yazı tipini desteklemez.  
  
-   İletişim kutuları için yazı tipi seçerken, kullanmak [MS Kabuk iletişim kutusu](http://msdn.microsoft.com/library/windows/desktop/dd374112) MS Sans Serif veya Helvetica yerine. MS Kabuk iletişim kutusu ile doğru yazı tipi iletişim kutusu oluşturmadan önce sistem tarafından değiştirilir. MS Kabuk iletişim kutusu kullanılarak bu yazı tipi ile mücadele etmek için işletim sisteminde değişiklikleri otomatik olarak kullanılabilir olmasını sağlar. (Bu sistemleri MS Kabuk iletişim kutusu doğru şekilde işlemez çünkü MFC MS Kabuk iletişim kutusu DEFAULT_GUI_FONT veya sistem yazı tipi Windows 95, Windows 98 ve Windows NT 4 ile değiştirir.)  
  
-   Uygulamanızı tasarlarken hangi dizeleri yerelleştirilmiş karar verin. Emin değilseniz, verilen herhangi bir dize yerelleştirilmiş olduğunu varsayalım. Bu nedenle, yerelleştirilebilir dizeler yerelleştirilemeyen karışık kullanmayın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MBCS programlama ipuçları](../text/mbcs-programming-tips.md)   
 [İşaretçileri Artırma ve Azaltma](../text/incrementing-and-decrementing-pointers.md)