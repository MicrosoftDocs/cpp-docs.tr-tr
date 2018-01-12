---
title: "Kalıcı olmayan iletişim kutuları oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MFC dialog boxes [MFC], modeless
- modeless dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
ms.assetid: 70d78c7f-3d40-477b-9f78-0f33c359f88b
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0549f898a076b140e7b5bed23c1c1e8c60d6adba
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="creating-modeless-dialog-boxes"></a>Kalıcı Olmayan İletişim Kutuları Oluşturma
Kalıcı olmayan iletişim kutusu için kendi ortak oluşturucu iletişim sınıfınızı sağlamanız gerekir. Kalıcı olmayan iletişim kutusu oluşturmak için ortak oluşturucu çağırın ve iletişim nesnenin çağrısı [oluşturma](../mfc/reference/cdialog-class.md#create) üye işlevi iletişim kaynağı yüklenemiyor. Çağırabilirsiniz **oluşturma** sırasında veya sonrasında oluşturucu çağrısı. İletişim kaynağını özelliğine sahipse **ws_vısıble**, hemen iletişim kutusu görüntülenir. Değilse, çağırmalısınız, kendi [ShowWindow](../mfc/reference/cwnd-class.md#showwindow) üye işlevi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bir İletişim Kutusunun Yaşam Döngüsü](../mfc/life-cycle-of-a-dialog-box.md)

