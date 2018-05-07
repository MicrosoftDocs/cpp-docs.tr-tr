---
title: 'Nasıl yapılır: yeniden başlatma Yöneticisi desteği ekleme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Restart manager [MFC]
- C++, application crash support
ms.assetid: 7f3f5867-d4bc-4ba8-b3c9-dc1e7be93642
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2a2916bd96bf36333a81b2e8a88e62cc8f562e9e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-add-restart-manager-support"></a>Nasıl yapılır: Yeniden Başlatma Yöneticisi Desteği Ekleme

Yeniden başlatma Yöneticisi'ni, Visual Studio için Windows Vista veya sonraki işletim sistemlerine eklenen bir özelliktir. Yeniden başlatma Yöneticisi beklenmedik şekilde kapatır veya yeniden uygulamanız için destek ekler. Yeniden başlatma Yöneticisi davranışını, uygulama türüne bağlıdır. Uygulamanız bir belge Düzenleyicisi ise, durumu otomatik olarak kaydetmek, uygulamanızın yeniden başlatma Yöneticisi etkin ve tüm açık içeriği belgeler ve uygulamanızı beklenmeyen kapatma sonrasında yeniden başlatır. Uygulamanızı bir belge Düzenleyicisi değilse, yeniden başlatma Yöneticisi uygulama yeniden başlatır, ancak varsayılan olarak uygulama durumunun kaydedilemiyor.  
  
 Uygulama Unicode ise yeniden başladıktan sonra uygulama bir görev iletişim kutusu görüntüler. ANSI uygulama ise, uygulama bir Windows ileti kutusu görüntüler. Bu noktada, kullanıcının otomatik kaydedilmiş belgeleri geri verilip seçer. Kullanıcı otomatik kaydedilmiş belgeleri geri yüklemez, yeniden başlatma Yöneticisi geçici dosyalar atar.  
  
> [!NOTE]
>  Verileri kaydetme ve uygulamayı yeniden başlatma için yeniden başlatma Yöneticisi'nin varsayılan davranışı geçersiz kılabilirsiniz.  
  
 Varsayılan olarak, MFC Uygulama Projesi Sihirbazı'nda kullanılarak oluşturulan [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] uygulamaları, Windows Vista veya sonraki bir işletim sistemi olan bir bilgisayarda çalıştırdığınızda yeniden başlatma Yöneticisi'ni destekler. Uygulamanızı yeniden başlatma Yöneticisi'ni destekleyecek şekilde istemiyorsanız, yeniden başlatma Yöneticisi'nde Yeni Proje Sihirbazı'nı devre dışı bırakabilirsiniz.  
  
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

