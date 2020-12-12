---
description: 'Daha fazla bilgi edinin: sunucular: In-Place çerçeve pencereleri uygulama'
title: 'Sunucular: Yerinde Çerçeve Pencereleri Uygulama'
ms.date: 09/09/2019
helpviewer_keywords:
- frame windows [MFC], implementing
- OLE server applications [MFC], frame windows
- servers, in-place frame windows
- frame windows [MFC], in-place
- in-place frame windows
ms.assetid: 09bde4d8-15e2-4fba-8d14-9b954d926b92
ms.openlocfilehash: 859a31bf107162aea6adb4d40ccf7b7b87f485b5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217360"
---
# <a name="servers-implementing-in-place-frame-windows"></a>Sunucular: Yerinde Çerçeve Pencereleri Uygulama

Bu makalede, sunucu uygulamanızı oluşturmak için uygulama Sihirbazı 'nı kullanmıyorsanız, Visual Editing Server uygulamanızda yerinde çerçeve pencerelerini uygulamak için yapmanız gerekenler açıklanmaktadır. Bu makalede özetlenen yordamın ardından, uygulama Sihirbazı tarafından oluşturulan uygulamadan veya Visual C++ birlikte sunulan bir örnekten mevcut bir yerinde çerçeve pencere sınıfı kullanabilirsiniz.

#### <a name="to-declare-an-in-place-frame-window-class"></a>Yerinde çerçeve pencere sınıfı bildirmek için

1. Konumundan bir yerinde kare pencere sınıfı türetirsiniz `COleIPFrameWnd` .

   - Sınıf üst bilgi dosyanızdaki DECLARE_DYNCREATE makrosunu kullanın.

   - Sınıf uygulama (. cpp) dosyanızdaki IMPLEMENT_DYNCREATE makrosunu kullanın. Bu, bu sınıfın nesnelerinin çerçeve tarafından oluşturulmasına izin verir.

1. `COleResizeBar`Çerçeve pencere sınıfında bir üye bildirin. Sunucu uygulamalarında yerinde yeniden boyutlandırmayı desteklemek istiyorsanız bu gereklidir.

   Bir `OnCreate` ileti işleyicisi bildirin ( [sınıf Sihirbazı 'nı](reference/mfc-class-wizard.md)kullanarak) ve `Create` `COleResizeBar` onu tanımladıysanız, üyeye yönelik çağrı yapın.

1. Bir araç çubuğudur varsa, `CToolBar` çerçeve pencere sınıfında bir üye bildirin.

   `OnCreateControlBars`Sunucu etkin olduğunda bir araç çubuğu oluşturmak için üye işlevini geçersiz kılın. Örneğin:

   [!code-cpp[NVC_MFCOleServer#1](../mfc/codesnippet/cpp/servers-implementing-in-place-frame-windows_1.cpp)]

   5. adımda bu kodun tartışmalarına bakın.

1. Ana. cpp dosyanıza bu yerinde çerçeve pencere sınıfı için üst bilgi dosyasını ekleyin.

1. `InitInstance`Uygulama sınıfınız için içinde, `SetServerInfo` açık ve yerinde düzenlemede kullanılacak kaynakları ve yerinde çerçeve penceresini belirtmek için belge şablonu nesnesinin işlevini çağırın.

Deyimdeki işlev çağrılarının serisi, **`if`** araç çubuğunu, sunucu tarafından belirtilen kaynaklardan oluşturur. Bu noktada, araç çubuğu kapsayıcının pencere hiyerarşisinin bir parçasıdır. Bu araç çubuğu öğesinden türetildiğinden, `CToolBar` sahibi değiştirmediğiniz müddetçe, kendi iletilerini sahibine, kapsayıcı uygulamasının çerçeve penceresine geçilecektir. Çağrının gerekli olmasının nedeni budur `SetOwner` . Bu çağrı, komutların sunucunun yerinde çerçeve penceresinde gönderildiği pencereyi değiştirir ve iletilerin sunucuya geçirilmesine neden olur. Bu, sunucunun sağladığı araç çubuğundaki işlemlere tepki vermesini sağlar.

Toolbar bit eşlemin KIMLIĞI, sunucu uygulamanızda tanımlanan diğer yerinde kaynaklarla aynı olmalıdır. Bkz. [menüler ve kaynaklar: Ayrıntılar Için sunucu eklemeleri](../mfc/menus-and-resources-server-additions.md) .

Daha fazla bilgi için bkz. *sınıf kitaplığı başvurusunda* [Copaipframewnd](../mfc/reference/coleipframewnd-class.md), [COleResizeBar](../mfc/reference/coleresizebar-class.md)ve [CDocTemplate:: SetServerInfo](../mfc/reference/cdoctemplate-class.md#setserverinfo) .

## <a name="see-also"></a>Ayrıca bkz.

[Sunucular](../mfc/servers.md)<br/>
[Sunucular: sunucu uygulama](../mfc/servers-implementing-a-server.md)<br/>
[Sunucular: sunucu belgeleri uygulama](../mfc/servers-implementing-server-documents.md)<br/>
[Sunucular: sunucu öğeleri](../mfc/servers-server-items.md)
