---
title: Bir C++ Pencere Nesnesi ile bir HWND Arasındaki İlişkiler
ms.date: 11/19/2018
f1_keywords:
- HWND
helpviewer_keywords:
- Windows window [MFC]
- window objects [MFC], HWND and
- HWND [MFC]
- CWnd class [MFC], HWND
- HWND, window objects [MFC]
ms.assetid: f2e76340-6691-4ee6-9424-0345634a9469
ms.openlocfilehash: 8cf8856be7166768c507932184e257cf69b0eb35
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62309331"
---
# <a name="relationship-between-a-c-window-object-and-an-hwnd"></a>Bir C++ Pencere Nesnesi ile bir HWND Arasındaki İlişkiler

Pencerenin *nesne* C++ nesnesidir `CWnd` sınıfı (veya türetilmiş bir sınıf), programınızı doğrudan oluşturur. Bu, gelir ve yanıt programınızın oluşturucuyu ve yok edici çağrıları olarak geçer. Windows *penceresi*, öte yandan, bir donuk varsa sistem kaynaklarını tüketir ve bir pencere için karşılık gelen bir iç Windows veri yapısına işleyicisidir. Bir Windows penceresi "pencere tanıtıcısı" tanımlanır (`HWND`) ve sonra oluşturulan `CWnd` bir çağrı tarafından oluşturulan nesne `Create` sınıfının üye işlevinde `CWnd`. Pencerenin programı çağrısı veya bir kullanıcı eylemi yok. Pencere tanıtıcısı penceresi nesne depolanan *m_hWnd* üye değişkeni. Aşağıdaki şekil, C++ pencere nesnesi ile Windows penceresi arasındaki ilişkiyi gösterir. Pencereler oluşturma ele alınmıştır [oluşturma Windows](../mfc/creating-windows.md). Pencerelerini yok etme ele alınmıştır [pencere nesnelerini yok etme](../mfc/destroying-window-objects.md).

![CWnd pencere nesnesi ile elde edilen penceresi](../mfc/media/vc37fj1.gif "CWnd pencere nesnesi ile elde edilen penceresi") <br/>
Pencere nesnesi ile Windows penceresi

## <a name="see-also"></a>Ayrıca bkz.

[Pencere Nesneleri](../mfc/window-objects.md)
