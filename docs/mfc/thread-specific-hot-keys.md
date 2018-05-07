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
ms.openlocfilehash: bdd6cf2f2bb76c30f4cc00d75eb55d7d2c01fa7e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="thread-specific-hot-keys"></a>İş Parçacığına Özgü Sık Kullanılan Tuşlar
Bir uygulama bir iş parçacığına özgü sık kullanılan tuş ayarlar ([CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)) kullanarak Windows **RegisterHotKey** işlevi. Kullanıcı bir iş parçacığına özgü sık kullanılan tuş bastığında Windows yazılarını bir [WM_HOTKEY](http://msdn.microsoft.com/library/windows/desktop/ms646279) bir belirli iş parçacığının ileti sırası başlangıcına ileti. **WM_HOTKEY** ileti sanal anahtar kodu, shift durumu ve basıldı belirli sık kullanılan tuş kullanıcı tanımlı Kimliğini içerir. Standart sanal anahtar kodları listesi için Winuser.h bakın. Bu yöntem hakkında daha fazla bilgi için bkz: [RegisterHotKey](http://msdn.microsoft.com/library/windows/desktop/ms646309).  
  
 Shift durumu bayrakları çağrısında kullanılan Not **RegisterHotKey** olanlar tarafından döndürülen aynı değildir [GetHotKey](../mfc/reference/chotkeyctrl-class.md#gethotkey) üye işlevi; çağırmadanöncebubayraklarÇevirgerekecek**RegisterHotKey**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CHotKeyCtrl kullanma](../mfc/using-chotkeyctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

