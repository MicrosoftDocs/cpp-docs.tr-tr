---
title: Bir C++ pencere nesnesi ile bir HWND arasındaki | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- HWND
dev_langs:
- C++
helpviewer_keywords:
- Windows window [MFC]
- window objects [MFC], HWND and
- HWND [MFC]
- CWnd class [MFC], HWND
- HWND, window objects [MFC]
ms.assetid: f2e76340-6691-4ee6-9424-0345634a9469
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b51daa375c3c920443316b6e10b6415ee018fdb4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33385784"
---
# <a name="relationship-between-a-c-window-object-and-an-hwnd"></a>Bir C++ Pencere Nesnesi ile bir HWND Arasındaki İlişkiler
Pencerenin *nesne* C++ nesnesidir `CWnd` sınıfı (veya türetilmiş bir sınıf) doğrudan, programı oluşturan. Gelen ve yanıt programınızın oluşturucu ve yıkıcı çağrıları olarak geçer. Windows *penceresi*, diğer yandan, bir donuk bir pencere karşılık gelir ve sistem kaynaklarını varsa tüketir bir iç Windows veri yapısına işleyicisidir. Windows penceresi "pencere tanıtıcısı" tanımlanır (`HWND`) ve sonra oluşturulan `CWnd` nesnesi için bir çağrı tarafından oluşturulur **oluşturma** sınıfının üye işlevini `CWnd`. Pencere, programı çağrısı veya bir kullanıcının eylemi tarafından yok edilmesi. Bir pencere tanıtıcının penceresi nesnenin depolanan `m_hWnd` üye değişkeni. Aşağıdaki şekilde C++ pencere nesnesi ile Windows penceresi arasındaki ilişkiyi gösterir. Pencereler oluşturma ele alınmıştır [oluşturma Windows](../mfc/creating-windows.md). Pencereleri yok etme ele alınmıştır [pencere nesnelerini yok etme](../mfc/destroying-window-objects.md).  
  
 ![CWnd pencere nesnesi ve sonuçta elde edilen penceresi](../mfc/media/vc37fj1.gif "vc37fj1")  
Pencere nesnesi ile Windows penceresi  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Pencere Nesneleri](../mfc/window-objects.md)

