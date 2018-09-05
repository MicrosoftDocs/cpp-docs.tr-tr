---
title: 'Tn003: pencere Nesnelere Windows eşleme işleyicilerini | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.mapping
dev_langs:
- C++
helpviewer_keywords:
- TN003
- handle maps
- Windows handles to objects [MFC]
- mappings [MFC], Windows handles to objects
ms.assetid: fbea9f38-992c-4091-8dbc-f29e288617d6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b022c4c42a7373f9bfc23c1fff5be2c1317709de
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43692454"
---
# <a name="tn003-mapping-of-windows-handles-to-objects"></a>TN003: Pencere İşleyicilerini Nesnelere Eşleme
Bu Not MFC açıklar Windows eşleme desteği rutinleri C++ nesnelerinin tanıtıcıları nesne.  
  
## <a name="the-problem"></a>Sorun  
 Windows nesneler genellikle temsil edilir çeşitli tarafından [İŞLEMEK](/windows/desktop/WinProg/windows-data-types) nesneleri MFC sınıfları sarmalamak Windows nesne tutamaçları ile C++ nesne. MFC sınıf kitaplığı işlevleri sarmalama tanıtıcı belirli bir tanıtıcı Windows nesnesi sarmalama C++ nesne bulmanızı sağlar. Ancak, bazen bir nesnenin bir C++ sarmalayıcı nesnesini yok ve bu saatlerde sistem C++ sarmalayıcı görev yapacak geçici bir nesne oluşturur.  
  
 Tanıtıcı eşlemeleri kullanan Windows nesneler aşağıdaki gibidir:  
  
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
  
 Bu nesnelerin herhangi biri için bir tanıtıcı göz önünde bulundurulduğunda, statik metodunu çağırarak tanıtıcı sarmalayan MFC nesne bulabilirsiniz `FromHandle`. Örneğin, adında bir HWND verilen *hWnd*, aşağıdaki satırı için bir işaretçi döndürür `CWnd` sonuna geldik *hWnd*:  
  
```  
CWnd::FromHandle(hWnd)  
```  
  
 Varsa *hWnd* geçici bir özel kapsayıcı nesnesi yok `CWnd` sarmalamak için oluşturulan *hWnd*. Geçerli bir C++ nesnesi herhangi bir tutamacı almak mümkün kılar.  
  
 Bir sarmalayıcı nesnesini oluşturduktan sonra bir ortak üye değişkeninin sarmalayıcı sınıfın tanıtıcısını alabilirsiniz. Durumunda, bir `CWnd`, *m_hWnd* HWND bu nesne içerir.  
  
## <a name="attaching-handles-to-mfc-objects"></a>MFC nesneleri tanıtıcıları ekleme  
 Yeni oluşturulan tanıtıcı sarmalayıcı nesnesine ve bir tanıtıcı bir Windows nesnesine verilen, çağırarak iki ilişkilendirebilirsiniz `Attach` Bu örnekte olduğu gibi işlev:  
  
```  
CWnd myWnd;  
myWnd.Attach(hWnd);
```  
  
 Bu ilişkilendirme kalıcı eşlem içinde bir giriş yapar *myWnd* ve *hWnd*. Çağırma `CWnd::FromHandle(hWnd)` artık bir işaretçi döndürür *myWnd*. Zaman *myWnd* olduğu silinmiş yıkıcı otomatik olarak silecektir *hWnd* Windows çağırarak [DestroyWindow](/windows/desktop/api/winuser/nf-winuser-destroywindow) işlevi. Bu istenmiyorsa *hWnd* gelen ayrılması *myWnd* önce *myWnd* yok (normalde kapsamda ayrılırken *myWnd*tanımlanmıştır). `Detach` Yöntemi bunu yapar.  
  
```  
myWnd.Detach();
```  
  
## <a name="more-about-temporary-objects"></a>Geçici nesneler hakkında daha fazla bilgi  
 Geçici nesneler oluşturulan her `FromHandle` zaten bir sarmalayıcı nesnesine sahip olmayan bir tanıtıcı verilir. Bu geçici nesneler, tanıtıcıdan kullanımdan çıkarıldı ve silen `DeleteTempMap` işlevleri. Varsayılan olarak [CWinThread::OnIdle](../mfc/reference/cwinthread-class.md#onidle) otomatik olarak çağıran `DeleteTempMap` geçici tanıtıcı eşlemeleri destekleyen her sınıf için. Bu, geçici bir nesne için bir işaretçi işaretçiyi nereye edinilen geçerli işlevden çıkış noktası geçmiş olacaktır varsayamazsınız anlamına gelir.  
  
## <a name="wrapper-objects-and-multiple-threads"></a>Sarmalayıcı nesneleri ve birden çok iş parçacığı  
 Geçici ve kalıcı nesneleri bir iş parçacığı başına temelinde korunur. Diğer bir deyişle, bir iş parçacığı, geçici veya kalıcı olmasına bakılmaksızın C++ sarmalayıcı nesneleri başka bir iş parçacığının, erişemez.  
  
 Bu nesneler bir iş parçacığından diğerine geçirmek için her zaman kendi yerel şirketlerde `HANDLE` türü. Bir iş parçacığından bir C++ sarmalayıcı nesnesini geçirerek genellikle beklenmeyen sonuçlara neden olur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)   
 [Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)

