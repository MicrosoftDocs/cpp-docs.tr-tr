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
ms.openlocfilehash: 8b30491b2cb46ab0e8b25edc2d39e6616817c9b4
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/14/2018
ms.locfileid: "42465723"
---
# <a name="how-to-add-restart-manager-support"></a>Nasıl yapılır: Yeniden Başlatma Yöneticisi Desteği Ekleme

Yeniden başlatma Yöneticisi, Visual Studio için Windows Vista veya sonraki işletim sistemlerine eklenen bir özelliktir. Beklenmedik bir şekilde kapatılır veya yeniden başlatır, yeniden başlatma Yöneticisi uygulamanız için destek ekler. Yeniden başlatma Yöneticisi davranışını, uygulamanın türüne bağlıdır. Uygulamanızı bir belge düzenleyicisine ise, durumu otomatik olarak kaydetmek uygulamanızı yeniden başlatma Yöneticisi etkin ve içeriği tüm açık belgeleri ve beklenmeyen bir kapatma sonrasında uygulamanızı yeniden başlatır. Uygulamanızı bir belge düzenleyicisine değil, yeniden başlatma Yöneticisi, uygulamayı yeniden başlatır, ancak varsayılan olarak uygulama durumunu kaydedemiyor.  
  
 Uygulama Unicode ise yeniden başlatma işleminden sonra uygulamayı bir görev iletişim kutusu görüntüler. ANSI uygulaması ise, uygulama Windows ileti kutusu görüntüler. Bu noktada, kullanıcının otomatik kaydedilmiş belgeleri geri verilip verilmeyeceğini seçer. Kullanıcı otomatik kaydedilmiş belgeleri geri yüklemez, yeniden başlatma Yöneticisi geçici dosyaları olarak atar.  
  
> [!NOTE]
>  Verileri kaydetme ve uygulamayı yeniden başlatma için yeniden başlatma Yöneticisi'nin varsayılan davranışı geçersiz kılabilirsiniz.  
  
 Uygulamaları, Windows Vista veya sonraki bir işletim sistemi olan bir bilgisayarda çalıştırdığınızda varsayılan olarak, Visual Studio'da Proje Sihirbazı kullanılarak oluşturulan MFC uygulamaları yeniden başlatma Yöneticisi'ni destekler. Yeniden başlatma Yöneticisi'ni desteklemek üzere uygulamanızı istemiyorsanız yeniden başlatma Yöneticisi'nde Yeni Proje Sihirbazı'nı devre dışı bırakabilirsiniz.  
  
### <a name="to-add-support-for-the-restart-manager-to-an-existing-application"></a>Mevcut bir uygulamaya yeniden başlatma Yöneticisi desteği eklemek için  
  
1.  Varolan bir MFC uygulamasına Visual Studio'da açın.  
  
2.  Ana uygulamanız için kaynak dosyasını açın. Varsayılan olarak bu uygulama ile aynı ada sahip .cpp dosyasıdır. Örneğin, ana uygulama kaynağı için MyProject MyProject.cpp dosyasıdır.  
  
3.  Oluşturucu ana uygulamanızı bulun. Örneğin, projeniz MyProject Oluşturucusu varsa, `CMyProjectApp::CMyProjectApp()`.  
  
4.  Aşağıdaki kod satırını, oluşturucuyu ekleyin.  
  
 ```  
    m_dwRestartManagerSupportFlags = AFX_RESTART_MANAGER_SUPPORT_ALL_ASPECTS;  
 ```  
  
5.  Emin `InitInstance` uygulamanızı yöntemini çağırır, üst `InitInstance` yöntemi: [CWinApp::InitInstance](../mfc/reference/cwinapp-class.md#initinstance) veya `CWinAppEx::InitInstance`. `InitInstance` Yöntemdir denetlemek için sorumlu *m_dwRestartManagerSupportFlags* parametresi.  
  
6.  Derleyin ve çalıştırın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CDataRecoveryHandler sınıfı](../mfc/reference/cdatarecoveryhandler-class.md)   
 [CWinApp::m_dwRestartManagerSupportFlags](../mfc/reference/cwinapp-class.md#m_dwrestartmanagersupportflags)   
 [CWinApp sınıfı](../mfc/reference/cwinapp-class.md)   
 [CWinApp::m_nAutosaveInterval](../mfc/reference/cwinapp-class.md#m_nautosaveinterval)   
 [CDocument::OnDocumentEvent](../mfc/reference/cdocument-class.md#ondocumentevent)

