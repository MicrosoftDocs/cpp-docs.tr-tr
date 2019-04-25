---
title: Kullanıcı Tanımlı Araçlar
ms.date: 11/19/2018
helpviewer_keywords:
- user-defined tools (MFC Extensions)
ms.assetid: cb887421-78ce-4652-bc67-96a53984ccaa
ms.openlocfilehash: 785e37c63653dde91176bedd0321fc58ac122c7e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62180838"
---
# <a name="user-defined-tools"></a>Kullanıcı Tanımlı Araçlar

MFC, kullanıcı tanımlı Araçlar destekler. Bir kullanıcı tanımlı araç bir harici, kullanıcı tarafından belirtilen programını yürüten özel bir komuttur. Özelleştirme işlemi, kullanıcı tanımlı Araçlar yönetmek için kullanabilirsiniz. Ancak, uygulama nesnenizin türünden türetilmediğinden varsa, bu işlem kullanamazsınız [CWinAppEx sınıfı](../mfc/reference/cwinappex-class.md). Özelleştirme hakkında daha fazla bilgi için bkz. [MFC için özelleştirme](../mfc/customization-for-mfc.md).

Kullanıcı tanımlı Araçlar desteği etkinleştirilirse, özelleştirme iletişim kutusunda otomatik olarak içerir **Araçları** sekmesi. Aşağıdaki çizimde gösterildiği **Araçları** sayfası.

![Araçlar sekmesindeki özelleştirme iletişim kutusunda](../mfc/media/custdialogboxtoolstab.png "araçları sekmede Özelleştir iletişim kutusu") <br/>
Özelleştirme iletişim kutusu araçları sekmesi

## <a name="enabling-user-defined-tools-support"></a>Kullanıcı tanımlı etkinleştirme desteği araçları

Kullanıcı tanımlı Araçlar uygulamada etkinleştirmek için çağrı [CWinAppEx::EnableUserTools](../mfc/reference/cwinappex-class.md#enableusertools). Ancak, bu çağrı için parametre olarak kullanılacak, uygulamanızın kaynak dosyalarındaki ilk birkaç sabitleri tanımlamalısınız.

Kaynak Düzenleyicisi'nde uygun komut kimliği kullanan işlevsiz bir komut oluşturun Aşağıdaki örnekte `ID_TOOLS_ENTRY` olarak komut kimliği. Bu komut kimliği framework kullanıcı tanımlı Araçlar nerede ekleyecek bir konumda bir veya daha fazla menüleri işaretler.

Kullanıcı tanımlı Araçlar temsil eden dize tablosunda art arda bazı kimlikler kenara ayarlamanız gerekir. Kullanıcılar tanımlayabilir kullanıcı araçlarını sayısı için kenara bırakmanızı dizeleri sayısı eşittir. Aşağıdaki örnekte, bu adlandırılmış `ID_USER_TOOL1` aracılığıyla `ID_USER_TOOL10`.

Öneriler, dizinler ve çağrılacak dış programları için bağımsız değişkenler araçları yardımcı olmak için kullanıcılara sunabilir. Bunu yapmak için kaynak Düzenleyicisi'nde iki açılır menüler oluşturma. Aşağıdaki örnekte bu adlandırılmış `IDR_MENU_ARGS` ve `IDR_MENU_DIRS`. Bu menülerde her komut için uygulama dize tablosunda bir dize tanımlar. Dize kaynak kimliği komut kimliğine eşit olmalıdır

Öğesinden türetilen bir sınıf oluşturabilirsiniz [CUserTool sınıfı](../mfc/reference/cusertool-class.md) varsayılan uygulama değiştirilecek. Bunu yapmak için RUNTIME_CLASS yerine CWinAppEx::EnableUserTools dördüncü parametre olarak, türetilmiş sınıf için çalışma zamanı bilgilerini geçirmek ([CUserTool sınıfı](../mfc/reference/cusertool-class.md)).

Uygun sabitleri tanımladıktan sonra çağırma [CWinAppEx::EnableUserTools](../mfc/reference/cwinappex-class.md#enableusertools) kullanıcı tanımlı Araçlar etkinleştirmek için.

Aşağıdaki yöntem çağrısını bu sabiti kullanma işlemini gösterir:

[!code-cpp[NVC_MFC_VisualStudioDemo#1](../mfc/codesnippet/cpp/user-defined-tools_1.cpp)]

Bu örnekte, Araçlar sekmesindeki dahil edilir **özelleştirme** iletişim kutusu. Framework komut kimliği eşleşen herhangi bir komutu yerini alacak `ID_TOOLS_ENTRY` bir kullanıcı bu menü açıldığında şu anda tanımlanmış kullanıcı araçlar kümesi ile herhangi bir menüde. Komut kimlikleri `ID_USER_TOOL1` aracılığıyla `ID_USER_TOOL10` kullanıcı tanımlı Araçlar kullanılmak için ayrılmıştır. Sınıf [CUserTool sınıfı](../mfc/reference/cusertool-class.md) kullanıcı araçlarını çağrılarını işler. Aracı sekmesinde **özelleştirme** iletişim kutusu sağlar menüleri erişim hakkı bağımsız değişken ve dizin girişi alanlarının düğmelere **IDR_MENU_ARGS** ve **IDR_MENU_DIRS**. Bir kullanıcı bu menüler birinden bir komutu seçtiğinde framework uygun metin kutusuna komutu kimliğine eşit kaynak kimliğinin dizesi ekler.

### <a name="including-predefined-tools"></a>Önceden tanımlanmış Araçlar dahil olmak üzere

Uygulama başlangıcında bazı araçlar ön tanımlamasında istiyorsanız, geçersiz kılmanız gerekir [CFrameWnd::LoadFrame](../mfc/reference/cframewnd-class.md#loadframe) uygulamanızın ana pencerenin yöntemi. Bu yöntemde, aşağıdaki adımları gerçekleştirmeniz gerekir.

##### <a name="to-add-new-tools-in-loadframe"></a>LoadFrame içinde yeni araçları eklemek için

1. Bir işaretçi alma [CUserToolsManager sınıfı](../mfc/reference/cusertoolsmanager-class.md) çağırarak [CWinAppEx::GetUserToolsManager](../mfc/reference/cwinappex-class.md#getusertoolsmanager).

1. Oluşturmak istediğiniz her aracı için çağrı [CUserToolsManager::CreateNewTool](../mfc/reference/cusertoolsmanager-class.md#createnewtool). Bu yöntem bir işaretçi döndürür. bir [CUserTool sınıfı](../mfc/reference/cusertool-class.md) nesne ve yeni oluşturulan kullanıcı aracı araçların iç koleksiyona ekler. Çalışma zamanı bilgileri türetilmiş bir sınıf için sağlamadığınızı [CUserTool sınıfı](../mfc/reference/cusertool-class.md) dördüncü parametre olarak [CWinAppEx::EnableUserTools](../mfc/reference/cwinappex-class.md#enableusertools), [CUserToolsManager::CreateNewTool](../mfc/reference/cusertoolsmanager-class.md#createnewtool) örneği oluşturmak ve bunun yerine bu sınıfın bir örneğini döndürür.

1. Her aracı için metin etiketini ayarlamak için `CUserTool::m_strLabel` komutunu çağırarak ayarlayın `CUserTool::SetCommand`. Varsayılan uygulaması [CUserTool sınıfı](../mfc/reference/cusertool-class.md) otomatik olarak yapılan çağrıda belirtilen program kullanılabilir simgeleri alır `SetCommand`.

## <a name="see-also"></a>Ayrıca bkz.

[MFC için Özelleştirme](../mfc/customization-for-mfc.md)<br/>
[CUserTool Sınıfı](../mfc/reference/cusertool-class.md)<br/>
[CUserToolsManager Sınıfı](../mfc/reference/cusertoolsmanager-class.md)<br/>
[CWinAppEx Sınıfı](../mfc/reference/cwinappex-class.md)
