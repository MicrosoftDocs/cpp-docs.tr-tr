---
title: "İleti türleri kullanıcı arabirimi nesneleri ile ilişkili | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.codewiz.uiobject.msgs
dev_langs:
- C++
helpviewer_keywords:
- message types and user interface objects [MFC]
ms.assetid: 681ee1a7-f6e6-4ea0-9fc6-1fb53a35516e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4ff4c7aac0c73406503df2f2384249279d3d7f97
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="message-types-associated-with-user-interface-objects"></a>Kullanıcı Arabirimi Nesneleri ile İlişkili İleti Türleri
Aşağıdaki tabloda, birlikte çalıştığınız nesne türlerini ve bunlarla ilişkili ileti türleri gösterilmektedir.  
  
### <a name="user-interface-objects-and-associated-messages"></a>Kullanıcı arabirimi nesneleri ve ilişkili iletileri  
  
|Nesne Kimliği|İletiler|  
|---------------|--------------|  
|Pencerenin temsil eden sınıf adı|Windows iletileri uygun için bir [CWnd](../../mfc/reference/cwnd-class.md)-türetilmiş sınıf: bir iletişim kutusu, penceresi, alt pencere, MDI alt pencere veya en üstteki çerçeve penceresi.|  
|Menü veya Hızlandırıcı tanımlayıcısı|-   **KOMUT** ileti (program işlevi çalıştırılır).<br />-   **UPDATE_COMMAND_UI** ileti (menü öğesi dinamik olarak güncelleştirir).|  
|Denetim tanımlayıcısı|Seçili denetim türü için denetimi bildirim iletileri.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İletileri işlevlere eşleme](../../mfc/reference/mapping-messages-to-functions.md)   
 [Kod sihirbazlarıyla işlevsellik ekleme](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Sınıf ekleme](../../ide/adding-a-class-visual-cpp.md)   
 [Üye işlevi ekleme](../../ide/adding-a-member-function-visual-cpp.md)   
 [Üye değişkeni ekleme](../../ide/adding-a-member-variable-visual-cpp.md)   
 [Sanal işlevi geçersiz kılma](../../ide/overriding-a-virtual-function-visual-cpp.md)   
 [MFC ileti işleyicisi](../../mfc/reference/adding-an-mfc-message-handler.md)   
 [Sınıf yapısında gezinme](../../ide/navigating-the-class-structure-visual-cpp.md)
