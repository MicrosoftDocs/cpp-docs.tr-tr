---
title: Kalıcı olmayan iletişim kutuları oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC dialog boxes [MFC], modeless
- modeless dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
ms.assetid: 70d78c7f-3d40-477b-9f78-0f33c359f88b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2055312c7418b14c9b274649db8faa297554257e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33340999"
---
# <a name="creating-modeless-dialog-boxes"></a>Kalıcı Olmayan İletişim Kutuları Oluşturma
Kalıcı olmayan iletişim kutusu için kendi ortak oluşturucu iletişim sınıfınızı sağlamanız gerekir. Kalıcı olmayan iletişim kutusu oluşturmak için ortak oluşturucu çağırın ve iletişim nesnenin çağrısı [oluşturma](../mfc/reference/cdialog-class.md#create) üye işlevi iletişim kaynağı yüklenemiyor. Çağırabilirsiniz **oluşturma** sırasında veya sonrasında oluşturucu çağrısı. İletişim kaynağını özelliğine sahipse **ws_vısıble**, hemen iletişim kutusu görüntülenir. Değilse, çağırmalısınız, kendi [ShowWindow](../mfc/reference/cwnd-class.md#showwindow) üye işlevi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bir İletişim Kutusunun Yaşam Döngüsü](../mfc/life-cycle-of-a-dialog-box.md)

