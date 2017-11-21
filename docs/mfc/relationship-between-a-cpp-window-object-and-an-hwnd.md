---
title: "Bir C++ pencere nesnesi ile bir HWND arasındaki | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: HWND
dev_langs: C++
helpviewer_keywords:
- Windows window [MFC]
- window objects [MFC], HWND and
- HWND [MFC]
- CWnd class [MFC], HWND
- HWND, window objects [MFC]
ms.assetid: f2e76340-6691-4ee6-9424-0345634a9469
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7f6e9da311a4141f50c49c8096ef9f0c95493c73
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="relationship-between-a-c-window-object-and-an-hwnd"></a>Bir C++ Pencere Nesnesi ile bir HWND Arasındaki İlişkiler
Pencerenin *nesne* C++ nesnesidir `CWnd` sınıfı (veya türetilmiş bir sınıf) doğrudan, programı oluşturan. Gelen ve yanıt programınızın oluşturucu ve yıkıcı çağrıları olarak geçer. Windows *penceresi*, diğer yandan, bir donuk bir pencere karşılık gelir ve sistem kaynaklarını varsa tüketir bir iç Windows veri yapısına işleyicisidir. Windows penceresi "pencere tanıtıcısı" tanımlanır (`HWND`) ve sonra oluşturulan `CWnd` nesnesi için bir çağrı tarafından oluşturulur **oluşturma** sınıfının üye işlevini `CWnd`. Pencere, programı çağrısı veya bir kullanıcının eylemi tarafından yok edilmesi. Bir pencere tanıtıcının penceresi nesnenin depolanan `m_hWnd` üye değişkeni. Aşağıdaki şekilde C++ pencere nesnesi ile Windows penceresi arasındaki ilişkiyi gösterir. Pencereler oluşturma ele alınmıştır [oluşturma Windows](../mfc/creating-windows.md). Pencereleri yok etme ele alınmıştır [pencere nesnelerini yok etme](../mfc/destroying-window-objects.md).  
  
 ![CWnd pencere nesnesi ve sonuçta elde edilen penceresi](../mfc/media/vc37fj1.gif "vc37fj1")  
Pencere nesnesi ile Windows penceresi  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Pencere nesneleri](../mfc/window-objects.md)

