---
title: 'Nasıl yapılır: Yeniden Başlatma Yöneticisi Desteği Ekleme'
ms.date: 11/04/2016
helpviewer_keywords:
- Restart manager [MFC]
- C++, application crash support
ms.assetid: 7f3f5867-d4bc-4ba8-b3c9-dc1e7be93642
ms.openlocfilehash: 848cb3bb52ae13eb1b7798126becd13384fddeb6
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84625661"
---
# <a name="how-to-add-restart-manager-support"></a>Nasıl yapılır: Yeniden Başlatma Yöneticisi Desteği Ekleme

Yeniden başlatma Yöneticisi, Windows Vista veya sonraki işletim sistemleri için Visual Studio 'ya eklenen bir özelliktir. Yeniden başlatma Yöneticisi, beklenmedik şekilde kapanmışsa veya yeniden başlatılırsa uygulamanız için destek ekler. Yeniden başlatma yöneticisinin davranışı uygulamanızın türüne bağlıdır. Uygulamanız belge Düzenleyicisi ise, yeniden başlatma Yöneticisi uygulamanızı açık belgelerin durumunu ve içeriğini otomatik olarak kaydetmek ve beklenmedik bir kapanışdan sonra uygulamanızı yeniden başlatmak üzere etkinleştirdi. Uygulamanız bir belge Düzenleyicisi değilse, yeniden başlatma Yöneticisi uygulamayı yeniden başlatır, ancak varsayılan olarak uygulamanın durumunu kaydedemez.

Yeniden başlattıktan sonra, uygulama Unicode ise, uygulama bir görev iletişim kutusu görüntüler. Bu bir ANSI uygulaması ise, uygulama bir Windows Ileti kutusu görüntüler. Bu noktada, Kullanıcı otomatik olarak kaydedilen belgelerin geri yüklenip yüklenmeyeceğini seçer. Kullanıcı otomatik olarak kaydedilen belgeleri geri yüklemez, yeniden başlatma Yöneticisi geçici dosyaları atar.

> [!NOTE]
> Yeniden başlatma yöneticisinin, verileri kaydetmek ve uygulamayı yeniden başlatmak için varsayılan davranışını geçersiz kılabilirsiniz.

Varsayılan olarak, Visual Studio 'da proje Sihirbazı kullanılarak oluşturulan MFC uygulamaları, uygulamalar Windows Vista veya üzeri işletim sistemine sahip bir bilgisayarda çalıştırıldığında yeniden başlatma yöneticisini destekler. Uygulamanızın yeniden başlatma yöneticisini desteklemesini istemiyorsanız, yeni proje sihirbazında yeniden başlatma yöneticisini devre dışı bırakabilirsiniz.

### <a name="to-add-support-for-the-restart-manager-to-an-existing-application"></a>Var olan bir uygulamaya yeniden başlatma Yöneticisi desteği eklemek için

1. Visual Studio 'da mevcut bir MFC uygulamasını açın.

1. Ana uygulamanız için kaynak dosyayı açın. Varsayılan olarak, uygulamanızla aynı ada sahip olan. cpp dosyasıdır. Örneğin, MyProject için ana uygulama kaynak dosyası Myprojem. cpp ' dir.

1. Ana uygulamanız için Oluşturucu bulun. Örneğin, projeniz projem ise, Oluşturucu olur `CMyProjectApp::CMyProjectApp()` .

1. Aşağıdaki kod satırını oluşturucuya ekleyin.

```
    m_dwRestartManagerSupportFlags = AFX_RESTART_MANAGER_SUPPORT_ALL_ASPECTS;
```

1. `InitInstance`Uygulamanızın yönteminin üst metodunu çağırtığınızdan emin olun `InitInstance` : [CWinApp:: InitInstance](reference/cwinapp-class.md#initinstance) veya `CWinAppEx::InitInstance` . `InitInstance`Yöntemi *m_dwRestartManagerSupportFlags* parametresini denetmaktan sorumludur.

1. Uygulamanızı derleyin ve çalıştırın.

## <a name="see-also"></a>Ayrıca bkz.

[CDataRecoveryHandler sınıfı](reference/cdatarecoveryhandler-class.md)<br/>
[CWinApp:: m_dwRestartManagerSupportFlags](reference/cwinapp-class.md#m_dwrestartmanagersupportflags)<br/>
[CWinApp Sınıfı](reference/cwinapp-class.md)<br/>
[CWinApp:: m_nAutosaveInterval](reference/cwinapp-class.md#m_nautosaveinterval)<br/>
[CDocument:: OnDocumentEvent](reference/cdocument-class.md#ondocumentevent)
