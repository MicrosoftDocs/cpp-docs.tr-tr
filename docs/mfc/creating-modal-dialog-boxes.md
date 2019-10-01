---
title: Kalıcı Iletişim kutuları oluşturma
ms.date: 11/04/2016
helpviewer_keywords:
- modal dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
- MFC dialog boxes [MFC], modal
ms.assetid: 26c7a68c-79f6-4862-a5a8-6024984644d2
ms.openlocfilehash: ed0fe3b7ef8aeddea01f573bfe8e1c01a6b5b443
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2019
ms.locfileid: "71685672"
---
# <a name="creating-modal-dialog-boxes"></a>Kalıcı Iletişim kutuları oluşturma

Kalıcı bir iletişim kutusu oluşturmak için [CDialog](../mfc/reference/cdialog-class.md)'da belirtilen iki ortak oluşturucudan birini çağırın. Ardından, iletişim kutusunu göstermek ve Kullanıcı Tamam ' ı seçinceye veya Iptal edilene kadar etkileşimi yönetmek için iletişim kutusu nesnesinin [DoModal](../mfc/reference/cdialog-class.md#domodal) üye işlevini çağırın. Bu yönetim `DoModal` ' dır ve iletişim kutusu kalıcı hale gelir. Kalıcı iletişim kutuları için, `DoModal` iletişim kutusu kaynağını yükler.

## <a name="see-also"></a>Ayrıca bkz.

[MFC 'de Iletişim kutularıyla çalışma](../mfc/life-cycle-of-a-dialog-box.md)
