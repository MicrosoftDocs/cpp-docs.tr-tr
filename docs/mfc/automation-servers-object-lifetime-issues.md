---
title: 'Otomasyon sunucuları: Nesne ömrü sorunları'
ms.date: 11/04/2016
helpviewer_keywords:
- objects [MFC], lifetime
- lifetime, automation server
- Automation servers, object lifetime
- servers, lifetime of Automation
ms.assetid: 342baacf-4015-4a0e-be2f-321424f1cb43
ms.openlocfilehash: f9dbc6e4f321ba10fdffa013c158d53b84331e30
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57293587"
---
# <a name="automation-servers-object-lifetime-issues"></a>Otomasyon sunucuları: Nesne ömrü sorunları

Bir otomasyon istemci oluşturur veya OLE öğesini etkinleştirir, sunucunun istemci o nesneye bir işaretçi geçirir. İstemci OLE işlevi yapılan bir çağrıyla nesnesine bir başvuru oluşturur [IUnknown::AddRef](/windows/desktop/api/unknwn/nf-unknwn-iunknown-addref). Bu başvuru istemci çağrıları kadar etkili olduğu [IUnknown::Release](/windows/desktop/api/unknwn/nf-unknwn-iunknown-release). (Microsoft Foundation Class Kitaplığı'nın OLE sınıfları ile yazılmış istemci uygulamaları bu çağrılar yapmamanız; çerçeve bunu yapar.) OLE sistemi ve sunucu nesne başvurular oluşturabilir. Bir sunucu, nesnenin yok nesne dış başvuruları geçerli kaldığı sürece.

Bir iç sayısı türetilen herhangi bir sunucu nesnenin başvuru sayısının framework tutar [CCmdTarget](../mfc/reference/ccmdtarget-class.md). Bu sayaç, bir otomasyon istemci güncelleştirilir veya başka bir varlık ekler veya nesnesine bir başvuru serbest bırakır.

Başvuru sayımı 0 olduğunda framework sanal işlev çağrıları [CCmdTarget::OnFinalRelease](../mfc/reference/ccmdtarget-class.md#onfinalrelease). Bu işlev varsayılan uygulamasını çağırır **Sil** işleci bu nesneyi silmek için.

Microsoft Foundation Class Kitaplığı uygulamanın nesnelere başvurular dış istemciniz olduğunda, uygulama davranışını denetlemek için ek olanakları sağlar. Her nesne başvuru sayısı Bakımı yanı sıra sunucuları etkin nesneler genel sayısını tutar. Genel işlevler [AfxOleLockApp](../mfc/reference/application-control.md#afxolelockapp) ve [AfxOleUnlockApp](../mfc/reference/application-control.md#afxoleunlockapp) güncelleştirme uygulama sayısı etkin bir nesne. Bu sayı sıfır değilse, kullanıcı sistem menüsünden veya çıkış Dosya menüsünden Kapat seçtiğinde uygulamayı sonlandırmak değil. Bunun yerine, uygulamanın ana pencere gizli (ancak yok edilmez) kadar tüm bekleyen istemci istekleri tamamlandı. Genellikle, `AfxOleLockApp` ve `AfxOleUnlockApp` oluşturucuları ve yıkıcıları, sırasıyla, Otomasyon destekleyen sınıfları adı verilir.

Bazen bir istemci yine de bir nesneye bir başvuru sahipken sonlandırmak için sunucu koşullar zorlar. Örneğin, sunucu bağımlı olduğu bir kaynak sunucunun hatayla karşılaşan kullanılamaz hale gelebilir. Kullanıcı aynı zamanda diğer uygulamaları başvuruları olan nesneler içeren bir sunucu belgesinin kapatabilirsiniz.

Bkz: Windows SDK'da `IUnknown::AddRef` ve `IUnknown::Release`.

## <a name="see-also"></a>Ayrıca bkz.

[Otomasyon Sunucuları](../mfc/automation-servers.md)<br/>
[AfxOleCanExitApp](../mfc/reference/application-control.md#afxolecanexitapp)
