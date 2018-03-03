---
title: "Kullanıcı tanımlı Araçlar | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- user-defined tools (MFC Extensions)
ms.assetid: cb887421-78ce-4652-bc67-96a53984ccaa
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 17f0751a2cb3f78730ec948d737dc99b85c2e735
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="user-defined-tools"></a>Kullanıcı Tanımlı Araçlar
MFC kullanıcı tanımlı Araçlar destekler. Kullanıcı tanımlı bir aracı bir dış, kullanıcı tarafından belirtilen programı yürüten özel bir komuttur. Özelleştirme işlemi, kullanıcı tanımlı Araçlar yönetmek için kullanabilirsiniz. Ancak, uygulama nesnesi türetilmedi varsa, bu işlem kullanamazsınız [CWinAppEx sınıfı](../mfc/reference/cwinappex-class.md). Özelleştirme hakkında daha fazla bilgi için bkz: [MFC için özelleştirme](../mfc/customization-for-mfc.md).  
  
 Kullanıcı tanımlı Araçlar desteği etkinleştirilirse, özelleştirme iletişim kutusu otomatik olarak içeren **Araçları** sekmesi. Aşağıdaki çizimde gösterildiği **Araçları** sayfası.  
  
 ![Araçlar sekmesinde Özelleştir iletişim kutusunda](../mfc/media/custdialogboxtoolstab.png "custdialogboxtoolstab")  
Özelleştirme iletişim kutusu araçları sekmesi  
  
## <a name="enabling-user-defined-tools-support"></a>Kullanıcı tanımlı etkinleştirme Destek Araçları  
 Kullanıcı tanımlı Araçlar uygulamada etkinleştirmek için arama [CWinAppEx::EnableUserTools](../mfc/reference/cwinappex-class.md#enableusertools). Ancak, bu çağrı için parametre olarak kullanmak için uygulamanızın kaynak dosyalarında ilk birkaç sabitleri tanımlamalısınız.  
  
 Kaynak Düzenleyicisi'nde uygun komut kimliği kullanan bir kukla komutu oluşturun Aşağıdaki örnekte, kullandığımız **ID_TOOLS_ENTRY** olarak komut kimliği. Bu komut kimliği framework kullanıcı tanımlı Araçlar burada ekleyecek bir konumda bir veya daha fazla menüleri işaretler.  
  
 Kullanıcı tanımlı Araçlar temsil eden dize tabloda art arda bazı kimlikler kenara ayarlamanız gerekir. Kullanıcılar tanımlayabilir kullanıcı araçlarını maksimum sayıya eşit, ayrılan dizeler, sayısıdır. Aşağıdaki örnekte, bunlar adlandırıldığı **ID_USER_TOOL1** aracılığıyla **ID_USER_TOOL10**.  
  
 Dizinler ve çağrılacağı dış programları için bağımsız değişken araçları seçin yardımcı olmak için kullanıcılara öneriler sunar. Bunu yapmak için kaynak düzenleyicisinde iki açılır menüler oluşturun. Aşağıdaki örnekte bu adlandırıldığı **IDR_MENU_ARGS** ve **IDR_MENU_DIRS**. Bu menülerde her komut için bir dize uygulama dize tablonuzda tanımlayın. Kaynak kimliği dizesi Komut Kimliği eşit olmalıdır  
  
 Türetilen bir sınıftan oluşturabilirsiniz [CUserTool sınıfı](../mfc/reference/cusertool-class.md) varsayılan uygulama değiştirmek için. Bunu yapmak için RUNTIME_CLASS yerine CWinAppEx::EnableUserTools dördüncü parametresi olarak çalışma zamanı bilgileri, türetilmiş bir sınıf için geçirin ([CUserTool sınıfı](../mfc/reference/cusertool-class.md)).  
  
 Uygun sabitleri tanımladıktan sonra çağrısı [CWinAppEx::EnableUserTools](../mfc/reference/cwinappex-class.md#enableusertools) kullanıcı tanımlı Araçlar etkinleştirmek için.  
  
 Aşağıdaki yöntem çağrısı bu sabitleri kullanmayı gösterir:  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#1](../mfc/codesnippet/cpp/user-defined-tools_1.cpp)]  
  
 Bu örnekte, Araçlar sekmesi üzerinde dahil edilecek **özelleştirme** iletişim kutusu. Framework komut kimliği eşleşen herhangi bir komuttan yerini alacak **ID_TOOLS_ENTRY** her bir kullanıcı o menüsü açtığında şu anda tanımlanmış kullanıcı araçları kümesiyle herhangi menüde. Komut kimlikleri **ID_USER_TOOL1** aracılığıyla **ID_USER_TOOL10** kullanıcı tanımlı araçlar için kullanılmak üzere ayrılmıştır. Sınıf [CUserTool sınıfı](../mfc/reference/cusertool-class.md) kullanıcı araçlarını çağrılarını işler. Aracı sekmesinde **özelleştirme** iletişim kutusu sağlar menüleri erişim hakkı bağımsız değişken ve dizin girişi alanlarının düğmelere **IDR_MENU_ARGS** ve **IDR_MENU_DIRS**. Bir kullanıcı bu menüler birinden bir komut seçtiğinde framework uygun metin kutusuna komut kimliği eşit kaynak kimliği olan dize ekler.  
  
### <a name="including-predefined-tools"></a>Önceden tanımlanmış araçları dahil olmak üzere  
 Uygulama başlangıç bazı araçlar önceden istiyorsanız, geçersiz kılmanız gerekir [CFrameWnd::LoadFrame](../mfc/reference/cframewnd-class.md#loadframe) , uygulamanızın ana penceresinin yöntemi. Bu yöntem, aşağıdaki adımları gerçekleştirmeniz gerekir.  
  
##### <a name="to-add-new-tools-in-loadframe"></a>LoadFrame içinde yeni araçları eklemek için  
  
1.  Bir işaretçi elde [CUserToolsManager sınıfı](../mfc/reference/cusertoolsmanager-class.md) çağırarak nesne [CWinAppEx::GetUserToolsManager](../mfc/reference/cwinappex-class.md#getusertoolsmanager).  
  
2.  Oluşturmak istediğiniz her aracı için çağrı [CUserToolsManager::CreateNewTool](../mfc/reference/cusertoolsmanager-class.md#createnewtool). Bu yöntem için bir işaretçi bir [CUserTool sınıfı](../mfc/reference/cusertool-class.md) nesne ve yeni oluşturulan kullanıcı aracı Araçlar iç koleksiyonuna ekler. Çalışma zamanı bilgileri türetilmiş bir sınıf için sağlanan varsa [CUserTool sınıfı](../mfc/reference/cusertool-class.md) dördüncü parametrenin olarak [CWinAppEx::EnableUserTools](../mfc/reference/cwinappex-class.md#enableusertools), [CUserToolsManager::CreateNewTool](../mfc/reference/cusertoolsmanager-class.md#createnewtool) örneği ve bunun yerine bu sınıfının bir örneğini döndürür.  
  
3.  Her aracı için metin etiketini ayarlamak için `CUserTool::m_strLabel` ve kendi komut aranarak `CUserTool::SetCommand`. Varsayılan uygulaması [CUserTool sınıfı](../mfc/reference/cusertool-class.md) otomatik olarak yapılan çağrıda belirtilen program kullanılabilir simgeleri alır `SetCommand`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC için özelleştirme](../mfc/customization-for-mfc.md)   
 [CUserTool sınıfı](../mfc/reference/cusertool-class.md)   
 [CUserToolsManager sınıfı](../mfc/reference/cusertoolsmanager-class.md)   
 [CWinAppEx Sınıfı](../mfc/reference/cwinappex-class.md)




