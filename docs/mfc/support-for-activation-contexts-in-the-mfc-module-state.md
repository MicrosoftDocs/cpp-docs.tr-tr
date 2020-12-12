---
description: Hakkında daha fazla bilgi için bkz. MFC modül durumunda etkinleştirme bağlamları desteği
title: MFC Modül Durumunda Etkinleştirme Bağlamları Desteği
ms.date: 11/04/2016
helpviewer_keywords:
- activation contexts [MFC]
- activation contexts [MFC], MFC support
ms.assetid: 1e49eea9-3620-46dd-bc5f-d664749567c7
ms.openlocfilehash: e7f7434824956ca2a62d75fbd50eb9dd5e01f34e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216476"
---
# <a name="support-for-activation-contexts-in-the-mfc-module-state"></a>MFC Modül Durumunda Etkinleştirme Bağlamları Desteği

MFC, kullanıcı modülü tarafından sağlanmış bir bildirim kaynağı kullanarak bir etkinleştirme bağlamı oluşturur. Etkinleştirme bağlamlarının nasıl oluşturulduğu hakkında daha fazla bilgi için aşağıdaki konulara bakın:

- [Etkinleştirme bağlamları](/windows/win32/SbsCs/activation-contexts)

- [Uygulama bildirimleri](/windows/win32/SbsCs/application-manifests)

- [Derleme bildirimleri](/windows/win32/SbsCs/assembly-manifests)

## <a name="remarks"></a>Açıklamalar

Bu Windows SDK konuları okunurken MFC etkinleştirme bağlam mekanizmasının, MFC 'nin Windows SDK etkinleştirme bağlamı API 'sini kullanmamasını hariç Windows SDK etkinleştirme bağlamına benzediğini unutmayın.

Etkinleştirme bağlamı MFC uygulamalarında, Kullanıcı dll 'Lerinde ve MFC uzantı dll 'Lerinde aşağıdaki yollarla çalışmaktadır:

- MFC uygulamaları, bildirim kaynakları için kaynak KIMLIĞI 1 ' i kullanır. Bu durumda, MFC kendi etkinleştirme bağlamını oluşturmaz, ancak varsayılan uygulama bağlamını kullanır.

- MFC Kullanıcı dll 'Leri, bildirim kaynakları için kaynak KIMLIĞI 2 kullanır. Burada MFC her Kullanıcı DLL için bir etkinleştirme bağlamı oluşturur, bu nedenle farklı kullanıcı dll 'Leri aynı kitaplıkların farklı sürümlerini (örneğin, ortak denetimler kitaplığı) kullanabilir.

- MFC uzantı dll 'Leri, etkinleştirme bağlamını oluşturmak için kendi barındırma uygulamalarını veya Kullanıcı dll 'Lerini kullanır.

Etkinleştirme bağlamı durumu, [etkinleştirme bağlamı API 'Si kullanılarak](/windows/win32/SbsCs/using-the-activation-context-api)açıklanan süreçler kullanılarak DEĞIŞTIRILEMIYORSA, MFC etkinleştirme bağlam mekanizmasını kullanmak, dış eklentilere tek tek çağrılar yapmadan önce ve sonra etkinleştirme durumunu el ile değiştirmek için kolay (veya mümkün olmayan) bir DLL tabanlı eklenti mimarileri geliştirirken yararlı olabilir.

Etkinleştirme bağlamı [Afxwininit](../mfc/reference/application-information-and-management.md#afxwininit)' de oluşturulur. Yok edicide yok edilir `AFX_MODULE_STATE` . Etkinleştirme bağlamı tanıtıcısı içinde tutulur `AFX_MODULE_STATE` . ( `AFX_MODULE_STATE` [AfxGetStaticModuleState](reference/extension-dll-macros.md#afxgetstaticmodulestate)içinde açıklanmaktadır.)

[AFX_MANAGE_STATE](reference/extension-dll-macros.md#afx_manage_state) makro etkinleştirme bağlamını etkinleştirir ve devre dışı bırakır. `AFX_MANAGE_STATE` , MFC kodunun Kullanıcı DLL tarafından seçilen uygun etkinleştirme bağlamında yürütülmesine izin vermek için, statik MFC kitaplıklarının yanı sıra MFC DLL 'Leri için de etkindir.

## <a name="see-also"></a>Ayrıca bkz.

[Etkinleştirme bağlamları](/windows/win32/SbsCs/activation-contexts)<br/>
[Uygulama bildirimleri](/windows/win32/SbsCs/application-manifests)<br/>
[Derleme bildirimleri](/windows/win32/SbsCs/assembly-manifests)<br/>
[AfxWinInit](../mfc/reference/application-information-and-management.md#afxwininit)<br/>
[AfxGetStaticModuleState](reference/extension-dll-macros.md#afxgetstaticmodulestate)<br/>
[AFX_MANAGE_STATE](reference/extension-dll-macros.md#afx_manage_state)
