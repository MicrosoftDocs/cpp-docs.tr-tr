---
title: Pencere nesneleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- objects [MFC], window
- Windows window [MFC]
- MFC, windows
- frame windows [MFC], C++ window objects
- window objects [MFC]
- windows [MFC], C++ window objects
- window messages [MFC]
- HWND
- messages [MFC], Windows
- Visual C++, window objects [MFC]
- HWND, window objects [MFC]
ms.assetid: 28b33ce2-af05-4617-9d03-1cb9a02be687
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 63b8d8dbde679d030eddd77fae6ca1fab519fdac
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33385277"
---
# <a name="window-objects"></a>Pencere Nesneleri
MFC sınıf sağlayan [CWnd](../mfc/reference/cwnd-class.md) yalıtılacak `HWND` bir pencere tanıtıcısı. `CWnd` Nesnesidir ayrı bir C++ pencere nesnesi, `HWND` temsil eden bir Windows penceresi ancak onu içeren. Kullanmak `CWnd` kendi alt pencere türetilen sınıflar ya da birçok MFC sınıfları birini kullanın türetilen `CWnd`. Sınıf `CWnd` çerçeve pencereleri, iletişim kutuları, alt öğe pencerelerini, denetimleri ve denetim çubukları araç çubukları gibi dahil olmak üzere tüm windows için temel sınıftır. İyi anlamış [bir C++ pencere nesnesi ile bir HWND arasındaki ilişkiyi](../mfc/relationship-between-a-cpp-window-object-and-an-hwnd.md) etkili programlama MFC için önemlidir.  
  
 MFC bazı varsayılan işlevselliği ve windows yönetim sağlar, ancak kendi sınıfından türetilen `CWnd` ve onun üye işlevleri sağlanan işlevselliği özelleştirmek için kullanın. Oluşturarak windows alt oluşturabilirsiniz bir `CWnd` nesne ve arama kendi [oluşturma](../mfc/reference/cwnd-class.md#create) üye işlev sonra kullanarak alt windows özelleştirme `CWnd` üye işlevleri. Öğesinden türetilen nesneler eklenebilir [CView](../mfc/reference/cview-class.md)form görünümleri veya bir çerçeve penceresinde ağaç görünümler gibi. Ve belgelerinizi sınıfı tarafından sağlanan Bölümlendirici bölmeleri aracılığıyla birden çok görünüm destekleyebilir [CSplitterWnd](../mfc/reference/csplitterwnd-class.md).  
  
 Her nesne sınıfından türetilen `CWnd` üzerinden Windows ileti eşlemesi veya kendi işleyicilerinizi komut kimlikleri bir ileti eşlemesi içerir.  
  
 Windows nasıl kullanılacağını öğrenmek için iyi bir kaynak için programlama üzerinde genel belgeleri `CWnd` kapsülleyen üye işlevleri `HWND` API'leri.  
  
## <a name="functions-for-operating-on-a-cwnd"></a>CWnd üzerinde işletim işlevleri  
 `CWnd` ve kendi [türetilen pencere sınıfları](../mfc/derived-window-classes.md) Oluşturucular, yok ediciler ve nesneyi başlatmak için üye işlevleri temel alınan Windows yapıları oluşturmak ve kapsüllenmiş erişim sağlayan `HWND`. `CWnd` Ayrıca Windows API'ları pencerenin durumu, güncelleştirme, koordinatları dönüştürme erişme ileti göndermek için kapsülleyen üye işlevleri sağlar kaydırma, Pano ve diğer pek çok görev erişme. Ele çoğu Windows pencere yönetimi API'leri bir `HWND` bağımsız değişkeni üye işlevlerini kapsüllenmiş `CWnd`. İşlevleri ve bunların parametrelerini adları olarak korunur `CWnd` üye işlevi. Windows API'larını yalıtılan hakkındaki ayrıntılar için `CWnd`, sınıfına bakın [CWnd](../mfc/reference/cwnd-class.md).  
  
## <a name="cwnd-and-windows-messages"></a>CWnd ve Windows iletileri  
 Birincil amaçlarından biri `CWnd` gibi Windows iletilerini işlemek için bir arabirim sağlamaktır `WM_PAINT` veya `WM_MOUSEMOVE`. Üye işlevlerini birçoğu `CWnd` standart iletileri için işleyiciler — bu tanımlayıcı ile başlayan **afx_msg** ve önek "," gibi `OnPaint` ve **OnMouseMove**. [İleti işleme ve eşleme](../mfc/message-handling-and-mapping.md) iletileri ve ileti işleme ayrıntılı olarak ele alınmaktadır. Bilgi var. framework'ün windows hem de özel amaçlar için kendiniz oluşturmanız için eşit oranda geçerlidir.  
  
### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz  
  
-   [Bir C++ pencere nesnesi ile bir HWND arasındaki ilişki](../mfc/relationship-between-a-cpp-window-object-and-an-hwnd.md)  
  
-   [Türetilen pencere sınıfları](../mfc/derived-window-classes.md)  
  
-   [Pencereler oluşturma](../mfc/creating-windows.md)  
  
-   [Pencere nesnelerini yok etme](../mfc/destroying-window-objects.md)  
  
-   [Bir CWnd'i HWND'inden Ayırma](../mfc/detaching-a-cwnd-from-its-hwnd.md)  
  
-   [Pencere nesneleriyle çalışma](../mfc/working-with-window-objects.md)  
  
-   [Cihaz bağlamları](../mfc/device-contexts.md): cihaz çizim Windows bağımsız duruma nesneleri  
  
-   [Grafik nesneleri](../mfc/graphic-objects.md): kalemler, Fırçalar, yazı tipleri, bit eşlemler, paletler, bölgeler  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Windows](../mfc/windows.md)

