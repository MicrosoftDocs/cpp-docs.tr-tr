---
title: 'Sunucular: Yerinde çerçeve pencerelerini uygulama'
ms.date: 09/09/2019
helpviewer_keywords:
- frame windows [MFC], implementing
- OLE server applications [MFC], frame windows
- servers, in-place frame windows
- frame windows [MFC], in-place
- in-place frame windows
ms.assetid: 09bde4d8-15e2-4fba-8d14-9b954d926b92
ms.openlocfilehash: bc5439003b7c891ac3f4000c9b7820746aec4c8d
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/11/2019
ms.locfileid: "70907539"
---
# <a name="servers-implementing-in-place-frame-windows"></a>Sunucular: Yerinde çerçeve pencerelerini uygulama

Bu makalede, sunucu uygulamanızı oluşturmak için uygulama Sihirbazı 'nı kullanmıyorsanız, Visual Editing Server uygulamanızda yerinde çerçeve pencerelerini uygulamak için yapmanız gerekenler açıklanmaktadır. Bu makalede özetlenen yordamın ardından, uygulama Sihirbazı tarafından oluşturulan uygulamadan veya Görselle C++birlikte sunulan bir örnekten mevcut bir yerinde çerçeve pencere sınıfı kullanabilirsiniz.

#### <a name="to-declare-an-in-place-frame-window-class"></a>Yerinde çerçeve pencere sınıfı bildirmek için

1. Konumundan `COleIPFrameWnd`bir yerinde kare pencere sınıfı türetirsiniz.

   - Sınıf üst bilgi dosyanızdaki DECLARE_DYNCREATE makrosunu kullanın.

   - Sınıf uygulama (. cpp) dosyanızdaki IMPLEMENT_DYNCREATE makrosunu kullanın. Bu, bu sınıfın nesnelerinin çerçeve tarafından oluşturulmasına izin verir.

1. Çerçeve pencere `COleResizeBar` sınıfında bir üye bildirin. Sunucu uygulamalarında yerinde yeniden boyutlandırmayı desteklemek istiyorsanız bu gereklidir.

   Bir `OnCreate` ileti işleyicisi bildirin ( [sınıf Sihirbazı 'nı](reference/mfc-class-wizard.md)kullanarak) `Create` `COleResizeBar` ve onu tanımladıysanız, üyeye yönelik çağrı yapın.

1. Bir araç çubuğudur varsa, çerçeve pencere `CToolBar` sınıfında bir üye bildirin.

   Sunucu etkin olduğunda bir araç çubuğu oluşturmak için üyeişlevinigeçersizkılın.`OnCreateControlBars` Örneğin:

   [!code-cpp[NVC_MFCOleServer#1](../mfc/codesnippet/cpp/servers-implementing-in-place-frame-windows_1.cpp)]

   5\. adımda bu kodun tartışmalarına bakın.

1. Ana. cpp dosyanıza bu yerinde çerçeve pencere sınıfı için üst bilgi dosyasını ekleyin.

1. Uygulama `InitInstance` sınıfınız için içinde, açık ve yerinde `SetServerInfo` düzenlemede kullanılacak kaynakları ve yerinde çerçeve penceresini belirtmek için belge şablonu nesnesinin işlevini çağırın.

**IF** deyimindeki işlev çağrılarının serisi, sunucu tarafından belirtilen kaynaklardan araç çubuğunu oluşturur. Bu noktada, araç çubuğu kapsayıcının pencere hiyerarşisinin bir parçasıdır. Bu araç çubuğu öğesinden `CToolBar`türetildiğinden, sahibi değiştirmediğiniz müddetçe, kendi iletilerini sahibine, kapsayıcı uygulamasının çerçeve penceresine geçilecektir. Çağrının `SetOwner` gerekli olmasının nedeni budur. Bu çağrı, komutların sunucunun yerinde çerçeve penceresinde gönderildiği pencereyi değiştirir ve iletilerin sunucuya geçirilmesine neden olur. Bu, sunucunun sağladığı araç çubuğundaki işlemlere tepki vermesini sağlar.

Toolbar bit eşlemin KIMLIĞI, sunucu uygulamanızda tanımlanan diğer yerinde kaynaklarla aynı olmalıdır. Bkz [. menüler ve kaynaklar: Ayrıntılar için](../mfc/menus-and-resources-server-additions.md) sunucu eklemeleri.

Daha fazla bilgi için bkz. *sınıf kitaplığı başvurusunda* [Copaipframewnd](../mfc/reference/coleipframewnd-class.md), [COleResizeBar](../mfc/reference/coleresizebar-class.md)ve [CDocTemplate:: SetServerInfo](../mfc/reference/cdoctemplate-class.md#setserverinfo) .

## <a name="see-also"></a>Ayrıca bkz.

[Sunucular](../mfc/servers.md)<br/>
[Sunucular: Sunucu Uygulama](../mfc/servers-implementing-a-server.md)<br/>
[Sunucular: Sunucu Belgeleri Uygulama](../mfc/servers-implementing-server-documents.md)<br/>
[Sunucular: Sunucu Öğeleri](../mfc/servers-server-items.md)
