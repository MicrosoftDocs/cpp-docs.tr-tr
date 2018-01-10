---
title: "Genel sık kullanılan tuşlar | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- keyboard shortcuts [MFC], hot keys
- CHotKeyCtrl class [MFC], global hot keys
- access keys [MFC], hot keys
- global hot keys [MFC]
ms.assetid: e0b95d14-c571-4c9a-9cd1-e7fc1f0e278d
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 82297507d8725e6292def759272f48d0d63e84b8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="global-hot-keys"></a>Genel Sık Kullanılan Tuşlar
Genel sık kullanılan tuş belirli nonchild penceresiyle ile ilişkilidir. Sistem herhangi bir kısmını penceresinden etkinleştirmek kullanıcının sağlar. Uygulamanın belirli bir pencere için genel bir kısayol tuşu göndererek ayarlar [WM_SETHOTKEY](http://msdn.microsoft.com/library/windows/desktop/ms646284) Bu pencere iletisi. Örneği için `m_HotKeyCtrl` olan [CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md) nesne ve `pMainWnd` gösteren bir işaretçidir pencereyi sık kullanılan tuş basıldığında etkinleştirilmesi için sık kullanılan tuş denetimi ile belirtilen ilişkilendirmek için aşağıdaki kodu kullanabilirsiniz tarafından için pencereyi işaret `pMainWnd`.  
  
 [!code-cpp[NVC_MFCControlLadenDialog#18](../mfc/codesnippet/cpp/global-hot-keys_1.cpp)]  
  
 Genel sık kullanılan tuş kullanıcı olduğunda, belirtilen pencere alan bir [WM_SYSCOMMAND](http://msdn.microsoft.com/library/windows/desktop/ms646360) belirten bir ileti **SC_HOTKEY** komut türü. Bu ileti ayrıca aldığı penceresi etkinleştirir. Bu ileti basıldı tam anahtar herhangi bir bilgi içermediği için bu yöntemi kullanarak aynı pencere için bağlı farklı sık kullanılan tuşlar arasında ayrım izin vermiyor. Sık kullanılan tuş gönderilen uygulama kadar geçerli kaldığı **WM_SETHOTKEY** çıkar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CHotKeyCtrl kullanma](../mfc/using-chotkeyctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

