---
description: 'Hakkında daha fazla bilgi edinin: Kullanıcı tanımlı araçlar'
title: Kullanıcı Tanımlı Araçlar
ms.date: 11/19/2018
helpviewer_keywords:
- user-defined tools (MFC Extensions)
ms.assetid: cb887421-78ce-4652-bc67-96a53984ccaa
ms.openlocfilehash: 4cccd0a68751a2f196c8c2e652088e8939e3f162
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97263640"
---
# <a name="user-defined-tools"></a>Kullanıcı Tanımlı Araçlar

MFC Kullanıcı tanımlı araçları destekler. Kullanıcı tanımlı bir araç, dış, Kullanıcı tarafından belirtilen bir programı yürüten özel bir komuttur. Kullanıcı tanımlı araçları yönetmek için özelleştirme sürecini kullanabilirsiniz. Ancak, uygulama nesneniz [CWinAppEx sınıfından](../mfc/reference/cwinappex-class.md)türetildiyse bu işlemi kullanamazsınız. Özelleştirme hakkında daha fazla bilgi için bkz. [MFC Için özelleştirme](../mfc/customization-for-mfc.md).

Kullanıcı tanımlı araçlar desteğini etkinleştirdiyseniz, özelleştirme iletişim kutusu **Araçlar** sekmesini otomatik olarak ekler. Aşağıdaki çizimde **Araçlar** sayfası gösterilmektedir.

![Özelleştir iletişim kutusundaki Araçlar sekmesi](../mfc/media/custdialogboxtoolstab.png "Özelleştir iletişim kutusundaki Araçlar sekmesi") <br/>
Özelleştirme iletişim kutusu Araçlar sekmesi

## <a name="enabling-user-defined-tools-support"></a>Kullanıcı tanımlı araç desteğini etkinleştirme

Bir uygulamada Kullanıcı tanımlı araçları etkinleştirmek için, [CWinAppEx:: EnableUserTools](../mfc/reference/cwinappex-class.md#enableusertools)komutunu çağırın. Ancak, öncelikle uygulamanızın kaynak dosyalarında bu çağrı için parametre olarak kullanılacak birkaç sabiti tanımlamanız gerekir.

Kaynak düzenleyicisinde, uygun bir komut KIMLIĞI kullanan bir kukla komut oluşturun. Aşağıdaki örnekte, `ID_TOOLS_ENTRY` komut kimliği olarak kullanırız. Bu komut KIMLIĞI, çerçevenin Kullanıcı tanımlı araçları ekleneceği bir veya daha fazla menülerde bir konum belirtir.

Kullanıcı tanımlı araçları temsil etmek için dize tablosunda ardışık bazı kimlikler ayarlamanız gerekir. Ayrılan dizelerin sayısı, kullanıcıların tanımlayabilirler en fazla Kullanıcı aracı sayısına eşittir. Aşağıdaki örnekte bunlar `ID_USER_TOOL1` ile adlandırılır `ID_USER_TOOL10` .

Kullanıcılara, araçlar olarak çağrılacak dış programların dizinlerini ve bağımsız değişkenlerini seçmesini sağlamak için öneriler sunabilirsiniz. Bunu yapmak için kaynak Düzenleyicisi 'nde iki açılan menü menüsü oluşturun. Aşağıdaki örnekte bunlar ve olarak adlandırılmıştır `IDR_MENU_ARGS` `IDR_MENU_DIRS` . Bu menülerdeki her komut için, uygulama dize tablonuzda bir dize tanımlayın. Dizenin kaynak KIMLIĞI, komut KIMLIĞINE eşit olmalıdır.

Ayrıca, varsayılan uygulamayı değiştirmek için [CUserTool sınıfından](../mfc/reference/cusertool-class.md) türetilmiş bir sınıf de oluşturabilirsiniz. Bunu yapmak için, türetilmiş sınıfınız için çalışma zamanı bilgilerini RUNTIME_CLASS ([CUserTool sınıfı](../mfc/reference/cusertool-class.md)) yerine CWinAppEx:: EnableUserTools içinde dördüncü parametre olarak geçirin.

Uygun sabitleri tanımladıktan sonra, Kullanıcı tanımlı araçları etkinleştirmek için [CWinAppEx:: EnableUserTools](../mfc/reference/cwinappex-class.md#enableusertools) komutunu çağırın.

Aşağıdaki yöntem çağrısı, bu sabitlerin nasıl kullanılacağını gösterir:

[!code-cpp[NVC_MFC_VisualStudioDemo#1](../mfc/codesnippet/cpp/user-defined-tools_1.cpp)]

Bu örnekte, Araçlar sekmesi **Özelleştirme** iletişim kutusuna dahil edilir. Çerçeve, `ID_TOOLS_ENTRY` bir Kullanıcı menüyü her açtığında, herhangi bir menüdeki komut kimliğiyle eşleşen komutu, tanımlı kullanıcı araçlarının kümesiyle değiştirecek. Aracılığıyla komut kimlikleri `ID_USER_TOOL1` `ID_USER_TOOL10` Kullanıcı tanımlı araçlar için kullanılmak üzere ayrılmıştır. [CUserTool sınıfı](../mfc/reference/cusertool-class.md) , Kullanıcı araçlarına yapılan çağrıları işler. **Özelleştirme** iletişim kutusunun araç sekmesi, **IDR_MENU_ARGS** ve **IDR_MENU_DIRS** menülere erişmek için bağımsız değişkenin ve Dizin girişi alanlarının sağ tarafındaki düğmeleri sağlar. Bir Kullanıcı bu menülerden bir komut seçtiğinde, çerçeve, kaynak KIMLIĞI komut KIMLIĞINE eşit olan dizeyi uygun metin kutusuna ekler.

### <a name="including-predefined-tools"></a>Önceden tanımlanmış araçları dahil etme

Uygulama başlangıcında bazı araçları önceden tanımlamak istiyorsanız, uygulamanızın ana penceresindeki [CFrameWnd:: LoadFrame](../mfc/reference/cframewnd-class.md#loadframe) metodunu geçersiz kılmanız gerekir. Bu yöntemde, aşağıdaki adımları gerçekleştirmeniz gerekir.

##### <a name="to-add-new-tools-in-loadframe"></a>LoadFrame 'e yeni araçlar eklemek için

1. [CWinAppEx:: Getuseraraçları yöneticisini](../mfc/reference/cwinappex-class.md#getusertoolsmanager)çağırarak [Cusermanagementmanager sınıfı](../mfc/reference/cusertoolsmanager-class.md) nesnesine bir işaretçi alın.

1. Oluşturmak istediğiniz her araç için, [Cuser, Manager:: CreateNewTool](../mfc/reference/cusertoolsmanager-class.md#createnewtool)' ı çağırın. Bu yöntem, bir [CUserTool sınıfı](../mfc/reference/cusertool-class.md) nesnesine bir işaretçi döndürür ve yeni oluşturulan kullanıcı aracını iç araç koleksiyonuna ekler. Bir [CUserTool sınıfının](../mfc/reference/cusertool-class.md) türetilmiş sınıfına ilişkin çalışma zamanı bilgilerini [CWinAppEx:: EnableUserTools](../mfc/reference/cwinappex-class.md#enableusertools)öğesinin dördüncü parametresi olarak sağladıysanız, [Cuseraraçlarý Manager:: CreateNewTool](../mfc/reference/cusertoolsmanager-class.md#createnewtool) bunun yerine bu sınıfın bir örneğini oluşturur ve döndürür.

1. Her araç için, öğesini çağırarak metin etiketini ayarlayın `CUserTool::m_strLabel` ve öğesini çağırarak komutunu ayarlayın `CUserTool::SetCommand` . [CUserTool sınıfının](../mfc/reference/cusertool-class.md) varsayılan uygulanması, ' ın ' de belirtilen programdan kullanılabilir simgeleri otomatik olarak alır `SetCommand` .

## <a name="see-also"></a>Ayrıca bkz.

[MFC için Özelleştirme](../mfc/customization-for-mfc.md)<br/>
[CUserTool sınıfı](../mfc/reference/cusertool-class.md)<br/>
[Cuser, yönetici sınıfı](../mfc/reference/cusertoolsmanager-class.md)<br/>
[CWinAppEx sınıfı](../mfc/reference/cwinappex-class.md)
