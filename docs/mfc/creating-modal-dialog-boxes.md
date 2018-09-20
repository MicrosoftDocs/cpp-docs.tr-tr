---
title: Kalıcı iletişim kutuları oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- modal dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
- MFC dialog boxes [MFC], modal
ms.assetid: 26c7a68c-79f6-4862-a5a8-6024984644d2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3fcc449a376091c07a7fb26b81fe19752bc3bcd6
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46376650"
---
# <a name="creating-modal-dialog-boxes"></a>Kalıcı İletişim Kutuları Oluşturma

Kalıcı bir iletişim kutusu oluşturmak için çağırın ya da bildirilen iki genel oluşturucular [CDialog](../mfc/reference/cdialog-class.md). Ardından, iletişim nesnenin çağrı [DoModal](../mfc/reference/cdialog-class.md#domodal) iletişim kutusunu görüntülemek ve onunla etkileşim Tamam kullanıcının seçtiği kadar yönetmek veya iptal üye işlevi. Bu yönetim tarafından `DoModal` ne iletişim kutusu kalıcı olmasını sağlar. Kalıcı iletişim kutuları için `DoModal` iletişim kutusu kaynağı yükler.

## <a name="see-also"></a>Ayrıca Bkz.

[Bir İletişim Kutusunun Yaşam Döngüsü](../mfc/life-cycle-of-a-dialog-box.md)

