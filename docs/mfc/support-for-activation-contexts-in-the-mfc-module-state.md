---
title: MFC Modül Durumunda Etkinleştirme Bağlamları Desteği
ms.date: 11/04/2016
helpviewer_keywords:
- activation contexts [MFC]
- activation contexts [MFC], MFC support
ms.assetid: 1e49eea9-3620-46dd-bc5f-d664749567c7
ms.openlocfilehash: a2e5f56eeb323f1bd5f20c5920bbdbe4a658554d
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57267868"
---
# <a name="support-for-activation-contexts-in-the-mfc-module-state"></a>MFC Modül Durumunda Etkinleştirme Bağlamları Desteği

MFC kullanıcı modülü tarafından sağlanan bir bildirim kaynağı kullanarak bir etkinleştirme bağlamı oluşturur. Etkinleştirme bağlamları nasıl oluşturulduğunu daha fazla bilgi için aşağıdaki konulara bakın:

- [Etkinleştirme bağlamları](/windows/desktop/SbsCs/activation-contexts)

- [Uygulama bildirimleri](/windows/desktop/SbsCs/application-manifests)

- [Derleme bildirimleri](/windows/desktop/SbsCs/assembly-manifests)

## <a name="remarks"></a>Açıklamalar

Bu Windows SDK'sı konular okurken, MFC, Windows SDK'yı etkinleştirme bağlamı API kullanmaz dışında MFC etkinleştirme bağlamı mekanizması Windows SDK'yı etkinleştirme bağlamı benzer unutmayın.

Etkinleştirme bağlamı MFC uygulamaları, kullanıcı DLL'ler ve MFC uzantısı DLL'leri şu şekilde çalışır:

- MFC uygulamaları için bildirim kendi kaynak kimliği 1 kaynağı kullanın. Bu durumda, MFC, kendi etkinleştirme bağlamı oluşturmaz, ancak varsayılan uygulama bağlamı kullanır.

- MFC kullanıcı DLL'leri, bildirim kaynağı için kaynak kimliği 2 kullanın. Burada, aynı kitaplıkları (örneğin, ortak denetimler kitaplığını) farklı sürümlerini farklı kullanıcı DLL'leri kullanabilmeniz için MFC her kullanıcı DLL için bir etkinleştirme bağlamı oluşturur.

- MFC uzantı DLL'leri barındırma uygulamalarına veya kullanıcı DLL'leri etkinleştirme bağlamları kurmak için kullanır.

Etkinleştirme bağlamı durumu altında açıklanan işlemlerde kullanarak değiştirilebilse [etkinleştirme bağlamı API'sini kullanarak](/windows/desktop/SbsCs/using-the-activation-context-api), MFC etkinleştirme bağlamı mekanizması kullanarak yararlı olabilir DLL tabanlı eklenti mimarileri geliştirirken olduğu değil kolay (veya mümkün değil) etkinleştirme durumu öncesinde ve sonrasında dış eklentileri için çağrıları tek tek el ile geçiş yapmak için.

Etkinleştirme bağlamı oluşturulan [Afxwinınit](../mfc/reference/application-information-and-management.md#afxwininit). İçinde yok `AFX_MODULE_STATE` yıkıcı. Etkinleştirme tanıtıcı tutulur `AFX_MODULE_STATE`. (`AFX_MODULE_STATE` açıklanan [AfxGetStaticModuleState](reference/extension-dll-macros.md#afxgetstaticmodulestate).)

[AFX_MANAGE_STATE](reference/extension-dll-macros.md#afx_manage_state) makrosu etkinleştirir ve etkinleştirme bağlamı'nı devre dışı bırakır. `AFX_MANAGE_STATE` statik MFC kitaplıkları, yanı sıra MFC DLL'leri kullanıcı DLL tarafından seçilen uygun etkinleştirme bağlamı yürütmek için MFC kodu izin vermek için etkinleştirilir.

## <a name="see-also"></a>Ayrıca bkz.

[Etkinleştirme bağlamları](/windows/desktop/SbsCs/activation-contexts)<br/>
[Uygulama bildirimleri](/windows/desktop/SbsCs/application-manifests)<br/>
[Derleme bildirimleri](/windows/desktop/SbsCs/assembly-manifests)<br/>
[AfxWinInit](../mfc/reference/application-information-and-management.md#afxwininit)<br/>
[AfxGetStaticModuleState](reference/extension-dll-macros.md#afxgetstaticmodulestate)<br/>
[AFX_MANAGE_STATE](reference/extension-dll-macros.md#afx_manage_state)
