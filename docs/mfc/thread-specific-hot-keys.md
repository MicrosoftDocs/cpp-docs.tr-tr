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
ms.openlocfilehash: f480b293e9c57e7fa189c6427ab39147681cfdaf
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43206866"
---
# <a name="thread-specific-hot-keys"></a>İş Parçacığına Özgü Sık Kullanılan Tuşlar
Bir uygulama bir iş parçacığına özgü sık kullanılan tuş ayarlar ([CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)) kullanarak Windows `RegisterHotKey` işlevi. Kullanıcı bir iş parçacığına özgü kısayol tuşuna bastığında Windows yazılarını bir [WM_HOTKEY](/windows/desktop/inputdev/wm-hotkey) başlangıcına bir belirli iş parçacığının ileti kuyruğu iletisi. Sanal anahtar kodu, kaydırma durumu ve kullanıcı tanımlı Kimliğini basıldığını belirli bir kısayol tuşu WM_HOTKEY ileti içerir. Winuser.h standart sanal anahtar kodlarının listesi için bkz. Bu yöntem hakkında daha fazla bilgi için bkz. [RegisterHotKey](https://msdn.microsoft.com/library/windows/desktop/ms646309).  
  
 Kaydırma durumu bayrakları çağrısında kullanılan Not `RegisterHotKey` olanlar tarafından döndürülen aynı değildir [GetHotKey](../mfc/reference/chotkeyctrl-class.md#gethotkey) ; üye işlevini çağırmadan önce bu bayraklar çevirmek zorunda kalırsınız `RegisterHotKey`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CHotKeyCtrl kullanma](../mfc/using-chotkeyctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

