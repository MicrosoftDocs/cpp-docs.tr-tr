---
title: Kalıcı İletişim Kutuları Oluşturma
ms.date: 11/04/2016
helpviewer_keywords:
- modal dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
- MFC dialog boxes [MFC], modal
ms.assetid: 26c7a68c-79f6-4862-a5a8-6024984644d2
ms.openlocfilehash: eb9aab7e8579fbbbfdf5d0f2dca9b6e6abea0066
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50657355"
---
# <a name="creating-modal-dialog-boxes"></a>Kalıcı İletişim Kutuları Oluşturma

Kalıcı bir iletişim kutusu oluşturmak için çağırın ya da bildirilen iki genel oluşturucular [CDialog](../mfc/reference/cdialog-class.md). Ardından, iletişim nesnenin çağrı [DoModal](../mfc/reference/cdialog-class.md#domodal) iletişim kutusunu görüntülemek ve onunla etkileşim Tamam kullanıcının seçtiği kadar yönetmek veya iptal üye işlevi. Bu yönetim tarafından `DoModal` ne iletişim kutusu kalıcı olmasını sağlar. Kalıcı iletişim kutuları için `DoModal` iletişim kutusu kaynağı yükler.

## <a name="see-also"></a>Ayrıca Bkz.

[Bir İletişim Kutusunun Yaşam Döngüsü](../mfc/life-cycle-of-a-dialog-box.md)

