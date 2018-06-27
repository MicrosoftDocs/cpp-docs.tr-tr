---
title: İş parçacığına özgü sık kullanılan tuşlar | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CHotKeyCtrl class [MFC], thread-specific hot keys
- keyboard shortcuts [MFC], hot keys
- threading [MFC], hot keys in CHotKeyCtrl
- access keys [MFC], hot keys
ms.assetid: b6021274-1498-483f-bcbf-ba5723547cc8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 14da7f0e5b0adbe72b6705700c1e9298751bc345
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36953615"
---
# <a name="thread-specific-hot-keys"></a>İş Parçacığına Özgü Sık Kullanılan Tuşlar
Bir uygulama bir iş parçacığına özgü sık kullanılan tuş ayarlar ([CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)) Windows kullanılarak `RegisterHotKey` işlevi. Kullanıcı bir iş parçacığına özgü sık kullanılan tuş bastığında Windows yazılarını bir [WM_HOTKEY](http://msdn.microsoft.com/library/windows/desktop/ms646279) bir belirli iş parçacığının ileti sırası başlangıcına ileti. WM_HOTKEY ileti sanal anahtar kodu, shift durumunu ve basıldı belirli sık kullanılan tuş kullanıcı tanımlı Kimliğini içerir. Standart sanal anahtar kodları listesi için Winuser.h bakın. Bu yöntem hakkında daha fazla bilgi için bkz: [RegisterHotKey](http://msdn.microsoft.com/library/windows/desktop/ms646309).  
  
 Shift durumu bayrakları çağrısında kullanılan Not `RegisterHotKey` olanlar tarafından döndürülen aynı değildir [GetHotKey](../mfc/reference/chotkeyctrl-class.md#gethotkey) üye işlevi; bu bayraklar çağırmadan önce çevir gerekecek `RegisterHotKey`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CHotKeyCtrl kullanma](../mfc/using-chotkeyctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

