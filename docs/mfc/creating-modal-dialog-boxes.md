---
description: 'Daha fazla bilgi edinin: kalıcı Iletişim kutuları oluşturma'
title: Kalıcı İletişim Kutuları Oluşturma
ms.date: 11/04/2016
helpviewer_keywords:
- modal dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
- MFC dialog boxes [MFC], modal
ms.assetid: 26c7a68c-79f6-4862-a5a8-6024984644d2
ms.openlocfilehash: 82fa10c65161df98ea3d377e302c0fb787feb14c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97309803"
---
# <a name="creating-modal-dialog-boxes"></a>Kalıcı İletişim Kutuları Oluşturma

Kalıcı bir iletişim kutusu oluşturmak için [CDialog](reference/cdialog-class.md)'da belirtilen iki ortak oluşturucudan birini çağırın. Ardından, iletişim kutusunu göstermek ve Kullanıcı Tamam ' ı seçinceye veya Iptal edilene kadar etkileşimi yönetmek için iletişim kutusu nesnesinin [DoModal](reference/cdialog-class.md#domodal) üye işlevini çağırın. Bu yönetim, `DoModal` iletişim kutusunu kalıcı hale getirir. Kalıcı iletişim kutuları için `DoModal` iletişim kutusu kaynağını yükler.

## <a name="see-also"></a>Ayrıca bkz.

[MFC’de İletişim Kutularıyla çalışma](life-cycle-of-a-dialog-box.md)
