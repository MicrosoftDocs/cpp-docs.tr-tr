---
title: "Nasıl yapılır: yeniden başlatma Yöneticisi desteği ekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- Restart manager [MFC]
- C++, application crash support
ms.assetid: 7f3f5867-d4bc-4ba8-b3c9-dc1e7be93642
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a413f28909a52e3bc82e9d8f2694d559bf8a885c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-add-restart-manager-support"></a>Nasıl yapılır: Yeniden Başlatma Yöneticisi Desteği Ekleme
Yeniden başlatma Yöneticisi eklenen bir özelliktir [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] için [!INCLUDE[wiprlhext](../c-runtime-library/reference/includes/wiprlhext_md.md)]. Yeniden başlatma Yöneticisi beklenmedik şekilde kapatır veya yeniden uygulamanız için destek ekler. Yeniden başlatma Yöneticisi davranışını, uygulama türüne bağlıdır. Uygulamanız bir belge Düzenleyicisi ise, durumu otomatik olarak kaydetmek, uygulamanızın yeniden başlatma Yöneticisi etkin ve tüm açık içeriği belgeler ve uygulamanızı beklenmeyen kapatma sonrasında yeniden başlatır. Uygulamanızı bir belge Düzenleyicisi değilse, yeniden başlatma Yöneticisi uygulama yeniden başlatır, ancak varsayılan olarak uygulama durumunun kaydedilemiyor.  
  
 Uygulama Unicode ise yeniden başladıktan sonra uygulama bir görev iletişim kutusu görüntüler. ANSI uygulama ise, uygulama bir Windows ileti kutusu görüntüler. Bu noktada, kullanıcının otomatik kaydedilmiş belgeleri geri verilip seçer. Kullanıcı otomatik kaydedilmiş belgeleri geri yüklemez, yeniden başlatma Yöneticisi geçici dosyalar atar.  
  
> [!NOTE]
>  Verileri kaydetme ve uygulamayı yeniden başlatma için yeniden başlatma Yöneticisi'nin varsayılan davranışı geçersiz kılabilirsiniz.  
  
 Varsayılan olarak, MFC Uygulama Projesi Sihirbazı'nda kullanılarak oluşturulan [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] uygulamaları olan bir bilgisayarda çalıştırdığınızda yeniden başlatma Yöneticisi'ni destekleyecek [!INCLUDE[wiprlhext](../c-runtime-library/reference/includes/wiprlhext_md.md)]. Uygulamanızı yeniden başlatma Yöneticisi'ni destekleyecek şekilde istemiyorsanız, yeniden başlatma Yöneticisi'nde Yeni Proje Sihirbazı'nı devre dışı bırakabilirsiniz.  
  
### <a name="to-add-support-for-the-restart-manager-to-an-existing-application"></a>Var olan bir uygulamayı yeniden başlatma Yöneticisi desteği ekleme  
  
1.  Varolan bir MFC uygulamasında açın [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)].  
  
2.  Ana uygulamanız için kaynak dosyasını açın. Varsayılan olarak bu, uygulamanızın aynı ada sahip .cpp dosyasıdır. Örneğin, ana uygulama kaynak MyProject MyProject.cpp dosyasıdır.  
  
3.  Oluşturucu ana uygulamanız için bulun. Örneğin, projenizin MyProject Oluşturucusu ise, `CMyProjectApp::CMyProjectApp()`.  
  
4.  Aşağıdaki kod satırını, oluşturucuyu ekleyin.  
  
 ```  
    m_dwRestartManagerSupportFlags = AFX_RESTART_MANAGER_SUPPORT_ALL_ASPECTS;  
 ```  
  
5.  Emin olun `InitInstance` uygulamanızın yöntemini çağıran üst `InitInstance` yöntemi: [CWinApp::InitInstance](../mfc/reference/cwinapp-class.md#initinstance) veya `CWinAppEx::InitInstance`. `InitInstance` Yöntemdir denetlemek için sorumlu `m_dwRestartManagerSupportFlags` parametresi.  
  
6.  Derleme ve uygulamanızı çalıştırın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CDataRecoveryHandler sınıfı](../mfc/reference/cdatarecoveryhandler-class.md)   
 [CWinApp::m_dwRestartManagerSupportFlags](../mfc/reference/cwinapp-class.md#m_dwrestartmanagersupportflags)   
 [CWinApp sınıfı](../mfc/reference/cwinapp-class.md)   
 [CWinApp::m_nAutosaveInterval](../mfc/reference/cwinapp-class.md#m_nautosaveinterval)   
 [CDocument::OnDocumentEvent](../mfc/reference/cdocument-class.md#ondocumentevent)

