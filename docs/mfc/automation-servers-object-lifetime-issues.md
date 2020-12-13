---
description: 'Daha fazla bilgi edinin: otomasyon sunucuları: Object-Lifetime sorunlar'
title: 'Otomasyon Sunucuları: Nesne Ömrü Sorunları'
ms.date: 11/04/2016
helpviewer_keywords:
- objects [MFC], lifetime
- lifetime, automation server
- Automation servers, object lifetime
- servers, lifetime of Automation
ms.assetid: 342baacf-4015-4a0e-be2f-321424f1cb43
ms.openlocfilehash: dd6f60766880f20715cd44f8531639ab78bcc86b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339858"
---
# <a name="automation-servers-object-lifetime-issues"></a>Otomasyon Sunucuları: Nesne Ömrü Sorunları

Bir Otomasyon istemcisi bir OLE öğesi oluşturduğunda veya etkinleştirdiğinde, sunucu istemciye bu nesneye bir işaretçi geçirir. İstemci, [IUnknown:: AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref)ole işlevine yapılan bir çağrı yoluyla nesnesine bir başvuru kurar. Bu başvuru, istemci [IUnknown:: Release](/windows/win32/api/unknwn/nf-unknwn-iunknown-release)öğesine çağrı yapana kadar geçerli olur. (Microsoft Foundation Class Kitaplığı OLE sınıflarıyla yazılan istemci uygulamalarının bu çağrıları yapması gerekmez; çerçeve bunu yapar.) OLE sistemi ve sunucu, nesnesine başvuru oluşturabilir. Nesneye yönelik dış başvurular etkin kaldığı sürece sunucu bir nesneyi yok etmez.

Framework, [CCmdTarget](reference/ccmdtarget-class.md)'dan türetilmiş herhangi bir sunucu nesnesine başvuru sayısı için bir iç sayı tutar. Bu sayı, bir Otomasyon istemcisi ya da başka bir varlık nesneye bir başvuru eklediğinde veya yayınlarsa güncelleştirilir.

Başvuru sayısı 0 olduğunda, çerçeve [CCmdTarget:: OnFinalRelease](reference/ccmdtarget-class.md#onfinalrelease)sanal işlevini çağırır. Bu işlevin varsayılan uygulanması, **`delete`** Bu nesneyi silmek için işlecini çağırır.

Microsoft Foundation Class Kitaplığı, dış istemciler uygulamanın nesnelerine başvurular olduğunda uygulama davranışını denetlemek için ek tesisler sağlar. Her bir nesneye başvuru sayısının korunmasının yanı sıra sunucular, etkin nesnelerin küresel sayısını korur. [AfxOleLockApp](reference/application-control.md#afxolelockapp) ve [AfxOleUnlockApp](reference/application-control.md#afxoleunlockapp) genel işlevleri uygulamanın etkin nesne sayısını güncelleştirir. Bu sayı sıfır değilse, Kullanıcı sistem menüsünden Kapat ' ı seçtiğinde veya Dosya menüsünden çıkarken uygulama sonlanmaz. Bunun yerine, bekleyen tüm istemci istekleri tamamlanana kadar uygulamanın ana penceresi gizlidir (ancak yok edilmez). Genellikle `AfxOleLockApp` ve, `AfxOleUnlockApp` otomasyonu destekleyen sınıfların sırasıyla oluşturucular ve Yıkıcılar içinde çağırılır.

Bazen, bir istemcinin hala bir nesne başvurusu olduğunda sunucuyu sonlanmaya zorlar. Örneğin, sunucunun bağlı olduğu bir kaynak kullanılamaz hale gelebilir ve sunucunun bir hatayla karşılaşmasına neden olur. Kullanıcı aynı zamanda diğer uygulamaların başvurduğu nesneleri içeren bir sunucu belgesini kapatabilir.

Windows SDK, bkz `IUnknown::AddRef` `IUnknown::Release` . ve.

## <a name="see-also"></a>Ayrıca bkz.

[Otomasyon sunucuları](automation-servers.md)<br/>
[AfxOleCanExitApp](reference/application-control.md#afxolecanexitapp)
