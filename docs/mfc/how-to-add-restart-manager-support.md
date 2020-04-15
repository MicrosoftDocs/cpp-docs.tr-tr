---
title: 'Nasıl yapılır: Yeniden Başlatma Yöneticisi Desteği Ekleme'
ms.date: 11/04/2016
helpviewer_keywords:
- Restart manager [MFC]
- C++, application crash support
ms.assetid: 7f3f5867-d4bc-4ba8-b3c9-dc1e7be93642
ms.openlocfilehash: 7cf3fede663a7c4bc85573e17dd9c2f8bf3622b4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373325"
---
# <a name="how-to-add-restart-manager-support"></a>Nasıl yapılır: Yeniden Başlatma Yöneticisi Desteği Ekleme

Yeniden başlatma yöneticisi, Visual Studio for Windows Vista veya daha sonraki işletim sistemleri için eklenen bir özelliktir. Yeniden başlatma yöneticisi, beklenmedik bir şekilde kapanırsa veya yeniden başlatılırsa uygulamanız için destek ekler. Yeniden başlatma yöneticisinin davranışı uygulamanızın türüne bağlıdır. Uygulamanız bir belge düzenleyicisiyse, yeniden başlatma yöneticisi uygulamanızın açık belgelerin durumunu ve içeriğini otomatik olarak kaydetmesini ve beklenmedik bir kapanıştan sonra uygulamanızı yeniden başlatmasını sağladı. Uygulamanız bir belge düzenleyicisi değilse, yeniden başlatma yöneticisi uygulamayı yeniden başlatacak, ancak varsayılan olarak uygulamanın durumunu kaydedemez.

Yeniden başlattıktan sonra, uygulama Unicode ise uygulama bir görev iletişim kutusu görüntüler. Bir ANSI uygulamasıysa, uygulama bir Windows İleti kutusu görüntüler. Bu noktada, kullanıcı otomatik olarak kaydedilen belgeleri geri yükleyip geri yüklememeyi seçer. Kullanıcı otomatik olarak kaydedilen belgeleri geri yüklemezse, yeniden başlatma yöneticisi geçici dosyaları atar.

> [!NOTE]
> Verileri kaydetmek ve uygulamayı yeniden başlatmak için yeniden başlatma yöneticisinin varsayılan davranışını geçersiz kılabilirsiniz.

Varsayılan olarak, Visual Studio'daki proje sihirbazı kullanılarak oluşturulan MFC uygulamaları, uygulamalar Windows Vista veya daha sonra işletim sistemine sahip bir bilgisayarda çalıştırıldığında yeniden başlatma yöneticisini destekler. Uygulamanızın yeniden başlatma yöneticisini desteklemesini istemiyorsanız, yeni proje sihirbazında yeniden başlatma yöneticisini devre dışı kullanabilirsiniz.

### <a name="to-add-support-for-the-restart-manager-to-an-existing-application"></a>Varolan Bir Uygulamaya Yeniden Başlatma Yöneticisi Için Destek Eklemek İçin

1. Visual Studio'da varolan bir MFC uygulamasını açın.

1. Ana uygulamanızın kaynak dosyasını açın. Varsayılan olarak bu, uygulamanızla aynı ada sahip .cpp dosyasıdır. Örneğin, MyProject için ana uygulama kaynak dosyası MyProject.cpp olduğunu.

1. Ana uygulamanız için oluşturucuyu bulun. Örneğin, projeniz MyProject ise, oluşturucu `CMyProjectApp::CMyProjectApp()`.

1. Oluşturucunuza aşağıdaki kod satırını ekleyin.

```
    m_dwRestartManagerSupportFlags = AFX_RESTART_MANAGER_SUPPORT_ALL_ASPECTS;
```

1. Uygulamanızın `InitInstance` yönteminin ana `InitInstance` yöntemini aradığından emin olun: [CWinApp::InitInstance](../mfc/reference/cwinapp-class.md#initinstance) veya `CWinAppEx::InitInstance`. `InitInstance` Yöntem, *m_dwRestartManagerSupportFlags* parametresini denetlemekten sorumludur.

1. Uygulamanızı derleyip çalıştırın.

## <a name="see-also"></a>Ayrıca bkz.

[CDataRecoveryHandler Sınıfı](../mfc/reference/cdatarecoveryhandler-class.md)<br/>
[CWinApp::m_dwRestartManagerSupportFlags](../mfc/reference/cwinapp-class.md#m_dwrestartmanagersupportflags)<br/>
[CWinApp Sınıfı](../mfc/reference/cwinapp-class.md)<br/>
[CWinApp::m_nAutosaveInterval](../mfc/reference/cwinapp-class.md#m_nautosaveinterval)<br/>
[Kdocument::OndocumentEvent](../mfc/reference/cdocument-class.md#ondocumentevent)
