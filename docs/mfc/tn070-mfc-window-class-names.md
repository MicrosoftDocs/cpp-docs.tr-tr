---
title: "TN070: MFC pencere sınıfı adları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.mfc.classes
dev_langs: C++
helpviewer_keywords:
- window class names [MFC]
- TN070 [MFC]
ms.assetid: 90617912-dd58-4a7c-9082-ced71736d7cd
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6a652d4306e01d15d49ae6f931041d3d5dd9909f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="tn070-mfc-window-class-names"></a>TN070: MFC Pencere Sınıfı Adları
> [!NOTE]
>  İlk çevrimiçi belgelerinde eklenmiştir beri aşağıdaki Teknik Not güncelleştirilmemiş. Sonuç olarak, bazı yordamlar ve konuları güncel veya yanlış olması olabilir. En son bilgiler için çevrimiçi belgeleri dizindeki ilgi konuyu aramak önerilir.  
  
 MFC windows penceresi özelliklerini yansıtan bir dinamik olarak oluşturulan sınıf adı kullanın. MFC sınıf adları çerçeve pencereleri, görünümler ve uygulama tarafından üretilen açılır pencereleri için dinamik olarak oluşturur. İletişim kutuları ve MFC Uygulama tarafından üretilen denetimleri penceresinin söz konusu sınıf için Windows tarafından sağlanan ad var.  
  
 Kendi pencere sınıfı kaydediliyor ve içinde geçersiz kılma kullanılarak dinamik olarak sağlanan sınıf adını değiştirebilirsiniz [PreCreateWindow](../mfc/reference/cwnd-class.md#precreatewindow). MFC tarafından sağlanan sınıf adlarını iki aşağıdaki biçimlerden birini uygun:  
  
```  
Afx:%x:%x  
Afx:%x:%x:%x:%x:%x  
```  
  
 Değiştir onaltılı basamak `%x` karakter doldurulur verilerden gelen [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) yapısı. MFC kullanan bu teknik böylece aynı gerektiren birden çok C++ sınıfları **WNDCLASS** yapıları aynı kayıtlı pencere sınıfı paylaşabilir. MFC uygulamaları tek en basit Win32 uygulamalardan farklı olarak, yüklü **WNDPROC**, kolayca paylaşabilmek için **WNDCLASS** süresi ve bellek kaydetmek için yapıları. Değiştirilebilir değerlerini `%x` yukarıda gösterilen karakterleri aşağıdaki gibidir:  
  
- **WNDCLASS.hInstance**  
  
- **WNDCLASS.style**  
  
- **WNDCLASS.hCursor**  
  
- **WNDCLASS.hbrBackground**  
  
- **WNDCLASS.hIcon**  
  
 İlk form (`Afx:%x:%x`) kullanıldığında **hCursor**, **hbrBackground**, ve **hIcon** tümü **NULL**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)   
 [Kategoriye göre teknik notlar](../mfc/technical-notes-by-category.md)   
 [: TN020 kimlik adlandırma ve numaralandırma kuralları](../mfc/tn020-id-naming-and-numbering-conventions.md)

