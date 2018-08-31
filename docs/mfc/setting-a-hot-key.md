---
title: Sık kullanılan tuş ayarlama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- keyboard shortcuts [MFC], hot keys
- access keys [MFC], hot keys
- CHotKeyCtrl class [MFC], setting hot key
ms.assetid: 6f3bc141-e346-4dce-9ca7-3e6b2c453f3f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 254d7532b83a4f30c0029b2488bb0b2111cce31d
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43219403"
---
# <a name="setting-a-hot-key"></a>Sık Kullanılan Tuş Ayarlama
Uygulamanız bir kısayol tuşu tarafından sağlanan bilgileri kullanabilir ([CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)) iki yoldan biriyle denetimi:  
  
-   Göndererek nonchild penceresi etkinleştirdiğiniz için genel sık kullanılan tuş ayarlama bir [WM_SETHOTKEY](/windows/desktop/inputdev/wm-sethotkey) etkinleştirilmesi için ileti penceresine.  
  
-   Windows işlevini çağırarak iş parçacığına özgü sık kullanılan tuş ayarlamak [RegisterHotKey](https://msdn.microsoft.com/library/windows/desktop/ms646309).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CHotKeyCtrl kullanma](../mfc/using-chotkeyctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

