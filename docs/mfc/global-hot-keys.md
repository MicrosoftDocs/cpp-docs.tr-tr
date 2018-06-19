---
title: Genel sık kullanılan tuşlar | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- keyboard shortcuts [MFC], hot keys
- CHotKeyCtrl class [MFC], global hot keys
- access keys [MFC], hot keys
- global hot keys [MFC]
ms.assetid: e0b95d14-c571-4c9a-9cd1-e7fc1f0e278d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cd597271d949770ec1a5871cad3ea7be0004e288
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33344236"
---
# <a name="global-hot-keys"></a>Genel Sık Kullanılan Tuşlar
Genel sık kullanılan tuş belirli nonchild penceresiyle ile ilişkilidir. Sistem herhangi bir kısmını penceresinden etkinleştirmek kullanıcının sağlar. Uygulamanın belirli bir pencere için genel bir kısayol tuşu göndererek ayarlar [WM_SETHOTKEY](http://msdn.microsoft.com/library/windows/desktop/ms646284) Bu pencere iletisi. Örneği için `m_HotKeyCtrl` olan [CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md) nesne ve `pMainWnd` gösteren bir işaretçidir pencereyi sık kullanılan tuş basıldığında etkinleştirilmesi için sık kullanılan tuş denetimi ile belirtilen ilişkilendirmek için aşağıdaki kodu kullanabilirsiniz tarafından için pencereyi işaret `pMainWnd`.  
  
 [!code-cpp[NVC_MFCControlLadenDialog#18](../mfc/codesnippet/cpp/global-hot-keys_1.cpp)]  
  
 Genel sık kullanılan tuş kullanıcı olduğunda, belirtilen pencere alan bir [WM_SYSCOMMAND](http://msdn.microsoft.com/library/windows/desktop/ms646360) belirten bir ileti **SC_HOTKEY** komut türü. Bu ileti ayrıca aldığı penceresi etkinleştirir. Bu ileti basıldı tam anahtar herhangi bir bilgi içermediği için bu yöntemi kullanarak aynı pencere için bağlı farklı sık kullanılan tuşlar arasında ayrım izin vermiyor. Sık kullanılan tuş gönderilen uygulama kadar geçerli kaldığı **WM_SETHOTKEY** çıkar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CHotKeyCtrl kullanma](../mfc/using-chotkeyctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

