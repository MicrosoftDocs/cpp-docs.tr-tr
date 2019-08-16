---
title: MFC Modül Durumunda Etkinleştirme Bağlamları Desteği
ms.date: 11/04/2016
helpviewer_keywords:
- activation contexts [MFC]
- activation contexts [MFC], MFC support
ms.assetid: 1e49eea9-3620-46dd-bc5f-d664749567c7
ms.openlocfilehash: 296df3d2ecec74c5c9a7deef1617298d40243724
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69511438"
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

Etkinleştirme bağlamı durumu, [etkinleştirme bağlamı API 'Si kullanılarak](/windows/win32/SbsCs/using-the-activation-context-api)açıklanan süreçler kullanılarak değiştirilemeyebilir, ancak, MFC etkinleştirme bağlam mekanizmasını kullanmak kolay olmayan DLL tabanlı eklenti mimarileri geliştirirken yararlı olabilir (veya mümkün değildir), dış eklentilere tek tek çağrılar yapmadan önce ve sonra etkinleştirme durumunu el ile değiştirin.

Etkinleştirme bağlamı [Afxwininit](../mfc/reference/application-information-and-management.md#afxwininit)' de oluşturulur. Yok `AFX_MODULE_STATE` edicide yok edilir. Etkinleştirme bağlamı tanıtıcısı içinde `AFX_MODULE_STATE`tutulur. (`AFX_MODULE_STATE` [AfxGetStaticModuleState](reference/extension-dll-macros.md#afxgetstaticmodulestate)içinde açıklanmaktadır.)

[AFX_MANAGE_STATE](reference/extension-dll-macros.md#afx_manage_state) makrosu etkinleştirme bağlamını etkinleştirir ve devre dışı bırakır. `AFX_MANAGE_STATE`, MFC kodunun Kullanıcı DLL tarafından seçilen uygun etkinleştirme bağlamında yürütülmesine izin vermek için, statik MFC kitaplıklarının yanı sıra MFC DLL 'Leri için de etkindir.

## <a name="see-also"></a>Ayrıca bkz.

[Etkinleştirme bağlamları](/windows/win32/SbsCs/activation-contexts)<br/>
[Uygulama bildirimleri](/windows/win32/SbsCs/application-manifests)<br/>
[Derleme bildirimleri](/windows/win32/SbsCs/assembly-manifests)<br/>
[AfxWinInit](../mfc/reference/application-information-and-management.md#afxwininit)<br/>
[AfxGetStaticModuleState](reference/extension-dll-macros.md#afxgetstaticmodulestate)<br/>
[AFX_MANAGE_STATE](reference/extension-dll-macros.md#afx_manage_state)
