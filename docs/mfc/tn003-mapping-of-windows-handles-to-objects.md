---
title: "TN003: İşleyicilerini nesnelere eşleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.mapping
dev_langs: C++
helpviewer_keywords:
- TN003
- handle maps
- Windows handles to objects [MFC]
- mappings [MFC], Windows handles to objects
ms.assetid: fbea9f38-992c-4091-8dbc-f29e288617d6
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7427ca7cbe6de30581153eb6d3269a83b9b456ed
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="tn003-mapping-of-windows-handles-to-objects"></a>TN003: Pencere İşleyicilerini Nesnelere Eşleme
MFC bu not açıklar Windows eşlemesi destek yordamları C++ nesneleri işleyicilerine nesne.  
  
## <a name="the-problem"></a>Sorun  
 Windows nesneleri genellikle temsil çeşitli tarafından [İŞLEMEK](http://msdn.microsoft.com/library/windows/desktop/aa383751) sarma Windows Nesne tanıtıcıları C++ nesneleri ile nesneleri MFC sınıfları. MFC sınıf kitaplığı işlevlerini kaydırma tanıtıcı belirli bir tanıtıcı olan Windows nesneyi kaydırma C++ nesne bulmanızı sağlar. Ancak, bazen bir nesne bir C++ kapsayıcı nesnesi yok ve bu saatlerde sistem C++ kapsayıcı olarak hareket edecek geçici bir nesne oluşturur.  
  
 Tanıtıcı eşlemeleri kullanan Windows nesneleri aşağıdaki gibidir:  
  
-   HWND ([CWnd](../mfc/reference/cwnd-class.md) ve `CWnd`-türetilmiş sınıflar)  
  
-   HDC ([CDC](../mfc/reference/cdc-class.md) ve `CDC`-türetilmiş sınıflar)  
  
-   HMENU ([CMenu](../mfc/reference/cmenu-class.md))  
  
-   HPEN ([CGdiObject](../mfc/reference/cgdiobject-class.md))  
  
-   HBRUSH (`CGdiObject`)  
  
-   HFONT (`CGdiObject`)  
  
-   HBITMAP (`CGdiObject`)  
  
-   HPALETTE (`CGdiObject`)  
  
-   HRGN (`CGdiObject`)  
  
-   HIMAGELIST ([Cımagelist](../mfc/reference/cimagelist-class.md))  
  
-   YUVA ([CSocket](../mfc/reference/csocket-class.md))  
  
 Bu nesnelerin herhangi biri için bir tanıtıcı verilen tanıtıcı statik yöntemini çağırarak sarmalar MFC nesne bulabilirsiniz `FromHandle`. Örneğin, adında bir HWND verilen `hWnd`, aşağıdaki satırı için bir işaretçi döndürülecek `CWnd` , sarmalar `hWnd`:  
  
```  
CWnd::FromHandle(hWnd)  
```  
  
 Varsa `hWnd` geçici bir özel uyarlama nesnesi yok `CWnd` sarmalamak için oluşturulan `hWnd`. Geçerli bir C++ nesnesi herhangi bir tutamacı almak mümkün kılar.  
  
 Bir sarmalayıcı nesnesini oluşturduktan sonra tanıtıcısını bir sarmalayıcı sınıfı ortak üye değişkeninden alabilir. Durumunda bir `CWnd`, `m_hWnd` bu nesne için HWND içerir.  
  
## <a name="attaching-handles-to-mfc-objects"></a>MFC nesneleri tanıtıcıları ekleme  
 Yeni oluşturulan tanıtıcı sarmalayıcı nesnesine ve bir tanıtıcı Windows nesnesine verilen, çağırarak iki ilişkilendirebilirsiniz `Attach` işlev bu örnekteki:  
  
```  
CWnd myWnd;  
myWnd.Attach(hWnd);
```  
  
 Bu ilişkilendirme kalıcı eşlemesine bir giriş yapar `myWnd` ve `hWnd`. Çağırma `CWnd::FromHandle(hWnd)` gösteren bir işaretçi şimdi döndürülecek `myWnd`. Zaman `myWnd` olduğu silinmiş yıkıcı otomatik olarak silecektir `hWnd` Windows çağırarak [DestroyWindow](http://msdn.microsoft.com/library/windows/desktop/ms632682) işlevi. Bu değil istenirse, `hWnd` gelen ayrılmış olmalıdır `myWnd` önce `myWnd` yok (normalde kapsamda ayrılırken `myWnd` tanımlandı). `Detach` Yöntemi bunu yapar.  
  
```  
myWnd.Detach();
```  
  
## <a name="more-about-temporary-objects"></a>Geçici nesneler hakkında daha fazla bilgi  
 Geçici nesneler oluşturulur her `FromHandle` bir sarmalayıcı nesnesi zaten sahip olmayan bir tanıtıcı verilir. Bu geçici nesneler kendi tanıtıcı ayrılmış ve silen `DeleteTempMap` işlevleri. Varsayılan olarak [CWinThread::OnIdle](../mfc/reference/cwinthread-class.md#onidle) otomatik olarak çağırır `DeleteTempMap` geçici tanıtıcı eşlemeleri destekleyen her sınıf için. Bu işaretçinin burada edinilen geçici bir nesne için bir işaretçi işlevden çıkış noktası geçmiş geçerli olmayacak varsayın olamaz anlamına gelir.  
  
## <a name="wrapper-objects-and-multiple-threads"></a>Sarmalayıcı nesneleri ve çoklu iş parçacıkları  
 Geçici ve kalıcı nesneler bir iş parçacığı başına temelinde korunur. Diğer bir deyişle, bir iş parçacığı geçici veya kalıcı olmasından bağımsız olarak başka bir iş parçacığının C++ kapsayıcı nesneleri, erişemiyor.  
  
 Bu nesneler bir iş parçacığından diğerine geçirmek için her zaman kendi yerel yollayarak `HANDLE` türü. C++ kapsayıcı nesnesinin bir iş parçacığından geçirme genellikle beklenmeyen sonuçlara neden olur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)   
 [Kategoriye göre teknik notlar](../mfc/technical-notes-by-category.md)

