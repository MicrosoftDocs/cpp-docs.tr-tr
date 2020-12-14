---
description: 'Hakkında daha fazla bilgi edinin: C++ pencere nesnesi ve HWND arasındaki Ilişki'
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
ms.openlocfilehash: bdcf52d2890265b854e3eef7854b489b47eda6a7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97218101"
---
# <a name="relationship-between-a-c-window-object-and-an-hwnd"></a>Bir C++ Pencere Nesnesi ile bir HWND Arasındaki İlişkiler

Pencere *nesnesi* , `CWnd` programınızın doğrudan oluşturduğu C++ sınıfının (veya türetilmiş bir sınıfın) bir nesnesidir. Bu, programınızın oluşturucusuna ve yıkıcı çağrılarına yanıt verir. Diğer yandan Windows *penceresi*, bir pencereye karşılık gelen ve mevcut olduğunda sistem kaynaklarını tüketen bir iç Windows veri yapısına yönelik donuk bir tanıtıcıdır. Bir Windows penceresi "pencere tutamacı" () tarafından tanımlanır `HWND` ve `CWnd` nesne, sınıfının üye işlevine yapılan bir çağrı tarafından oluşturulduktan sonra oluşturulur `Create` `CWnd` . Pencere, bir program çağrısıyla ya da bir kullanıcının eylemiyle yok edilebilir. Pencere tutamacı pencere nesnesinin *m_hWnd* üye değişkeninde depolanır. Aşağıdaki şekilde, C++ pencere nesnesi ve Windows penceresi arasındaki ilişki gösterilmektedir. Windows oluşturma, [Windows oluşturma](../mfc/creating-windows.md)konusunda ele alınmıştır. Windows yok edilirken [Pencere nesneleri yok edilirken](../mfc/destroying-window-objects.md)ele alınmıştır.

![CWnd pencere nesnesi ve ortaya çıkan pencere](../mfc/media/vc37fj1.gif "CWnd pencere nesnesi ve ortaya çıkan pencere") <br/>
Pencere nesnesi ve Windows penceresi

## <a name="see-also"></a>Ayrıca bkz.

[Pencere nesneleri](../mfc/window-objects.md)
