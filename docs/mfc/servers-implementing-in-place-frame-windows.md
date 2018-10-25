---
title: 'Sunucular: Yerinde çerçeve Windows uygulama | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- frame windows [MFC], implementing
- OLE server applications [MFC], frame windows
- servers, in-place frame windows
- frame windows [MFC], in-place
- in-place frame windows
ms.assetid: 09bde4d8-15e2-4fba-8d14-9b954d926b92
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e6ef01a7943bbb0c14ec630651757a8665373b85
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50055230"
---
# <a name="servers-implementing-in-place-frame-windows"></a>Sunucular: Yerinde Çerçeve Pencereleri Uygulama

Bu makalede, sunucu uygulamanızı oluşturmak için Uygulama Sihirbazı'nı kullanmıyorsanız, yerinde çerçeve pencereleri, bir görsel düzenleme sunucu uygulaması uygulamak için yapılması gereken açıklanmaktadır. Bu makalede açıklanan yordamı izleyerek yerine bir uygulama Sihirbazı tarafından oluşturulan bir uygulama ya da Visual C++ ile sağlanan bir örnek var olan bir yerinde çerçeve pencere sınıfı kullanabilirsiniz.

#### <a name="to-declare-an-in-place-frame-window-class"></a>Yerinde çerçeve pencere sınıf tanımlamak için

1. Bir yerinde çerçeve pencere sınıfından türetilir `COleIPFrameWnd`.

   - DECLARE_DYNCREATE makrosu sınıfı üst bilgi dosyanızda kullanın.

   - IMPLEMENT_DYNCREATE makrosu, sınıf uygulama (.cpp) dosyasında kullanın. Bu çerçeve tarafından oluşturulması, bu sınıfın nesneleri sağlar.

1. Bildirme bir `COleResizeBar` çerçeve penceresi sınıfında üyesi. Bu, sunucu uygulamalarında yerinde yeniden boyutlandırma desteklemek istiyorsanız gereklidir.

   Bildirme bir `OnCreate` ileti işleyicisi (kullanarak **özellikleri** pencere) ve çağrı `Create` için `COleResizeBar` varsa, tanımlanan üye.

1. Araç çubuğu varsa bildirmek bir `CToolBar` çerçeve penceresi sınıfında üyesi.

   Geçersiz kılma `OnCreateControlBars` sunucu yerinde etkin olduğunda, bir araç çubuğu oluşturmak için üye işlevi. Örneğin:

   [!code-cpp[NVC_MFCOleServer#1](../mfc/codesnippet/cpp/servers-implementing-in-place-frame-windows_1.cpp)]

   5. adım aşağıdaki Bu kod tartışmalara bakın.

1. Bu yerinde çerçeve-pencere sınıfı için üst bilgi dosyası ana .cpp dosyanıza ekleyin.

1. İçinde `InitInstance` uygulama sınıfınız için çağrı `SetServerInfo` belge şablon nesnesinin açık ve yerinde düzenleme kullanılacak yerinde çerçeve penceresini ve kaynakları belirtmek için işlev.

Bir dizi işlev çağrıları **varsa** deyimi kaynaklardan araç sağlanan sunucu oluşturur. Bu noktada, araç kapsayıcının pencere hiyerarşisi parçasıdır. Bu araç türetilmiş olduğundan `CToolBar`, sahibi değiştirmediğiniz sürece sahibi, kapsayıcı uygulamasının çerçeve penceresini, iletileri geçer. İşte bu çağrı `SetOwner` gereklidir. Bu çağrı, sunucunun yerinde çerçeve penceresi, sunucuya geçirilecek iletileri neden olacak şekilde komutları nereye gönderileceğini penceresini değiştirir. Bu işlemleri sağlar araç çubuğundaki tepki vermek sağlar.

Araç çubuğu bit eşlem kimliği server uygulamanızda tanımlanan diğer yerinde kaynakları aynı olması gerekir. Bkz: [menüler ve kaynaklar: sunucu ekleme](../mfc/menus-and-resources-server-additions.md) Ayrıntılar için.

Daha fazla bilgi için [Coleıpframewnd](../mfc/reference/coleipframewnd-class.md), [COleResizeBar](../mfc/reference/coleresizebar-class.md), ve [CDocTemplate::SetServerInfo](../mfc/reference/cdoctemplate-class.md#setserverinfo) içinde *sınıf kitaplığı başvurusu*.

## <a name="see-also"></a>Ayrıca Bkz.

[Sunucular](../mfc/servers.md)<br/>
[Sunucular: Sunucu Uygulama](../mfc/servers-implementing-a-server.md)<br/>
[Sunucular: Sunucu Belgeleri Uygulama](../mfc/servers-implementing-server-documents.md)<br/>
[Sunucular: Sunucu Öğeleri](../mfc/servers-server-items.md)

