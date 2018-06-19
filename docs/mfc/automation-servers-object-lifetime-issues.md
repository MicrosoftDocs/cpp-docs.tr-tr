---
title: 'Otomasyon sunucuları: Nesne ömrü sorunları | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- objects [MFC], lifetime
- lifetime, automation server
- Automation servers, object lifetime
- servers, lifetime of Automation
ms.assetid: 342baacf-4015-4a0e-be2f-321424f1cb43
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e27812c20a64f5472c29a66298bcdec30bf4ef2b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33341806"
---
# <a name="automation-servers-object-lifetime-issues"></a>Otomasyon Sunucuları: Nesne Ömrü Sorunları
Bir otomasyon istemci oluşturur veya OLE öğeyi etkinleştirir, sunucu bu nesne için bir işaretçi istemci geçirir. OLE işlevi çağrısı aracılığıyla nesneye başvuru istemci oluşturur [IUnknown::AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379). Bu başvuru istemci çağrılarını kadar etkili olduğu [IUnknown::Release](http://msdn.microsoft.com/library/windows/desktop/ms682317). (Microsoft Foundation Class Kitaplığı'nın OLE sınıfları ile yazılmış istemci uygulamaların bu çağrıları yapmamanız; framework bunu yapar.) OLE sistemi ve sunucu nesne başvuruları oluşturabilir. Bir sunucu, bir nesne yok nesne dış başvuruları etkin kaldığı sürece.  
  
 Bir iç sayısını türetilmiş herhangi bir sunucu nesnesi başvurular framework tutar [CCmdTarget](../mfc/reference/ccmdtarget-class.md). Bu sayaç bir otomasyon istemci onayladığında veya başka bir varlık ekler veya nesneye bir başvurusu serbest bırakır.  
  
 Başvuru sayısı 0 olduğunda framework sanal işlev çağrıları [CCmdTarget::OnFinalRelease](../mfc/reference/ccmdtarget-class.md#onfinalrelease). Bu işlev varsayılan uygulamasını çağıran **silmek** bu nesneyi silmek için işleci.  
  
 Microsoft Foundation Class Kitaplığı uygulamanın nesnelere başvurular dış istemciniz olduğunda uygulama davranışını denetlemek için ek olanakları sağlar. Her nesne başvuruları sayısını koruma yanı sıra sunucuları etkin nesneler genel sayısını bulundurur. Genel işlevler [AfxOleLockApp](../mfc/reference/application-control.md#afxolelockapp) ve [AfxOleUnlockApp](../mfc/reference/application-control.md#afxoleunlockapp) güncelleştirme etkin nesneler uygulamanın sayısı. Bu sayı sıfır değilse, kullanıcının sistem menüsünden veya Dosya menüsünden Çıkış Kapat seçtiğinde uygulamayı sonlandırmak değil. Bunun yerine, uygulamanın ana penceresi gizli (ancak değil yok) kadar tüm bekleyen istemci isteği tamamlandı. Genellikle, `AfxOleLockApp` ve `AfxOleUnlockApp` Kurucular ve Yıkıcılar, Otomasyon destekleyen sınıfları sırasıyla denir.  
  
 Bazen durumlarda bir istemci yine bir nesneye başvuru sahipken sonlandırmak için sunucu zorlar. Örneğin, sunucunun bağımlı olduğu bir kaynak sunucunun hatayla karşılaşırsanız neden kullanılamaz hale gelebilir. Kullanıcı aynı zamanda diğer uygulamaların başvuruları olan nesneleri içeren bir sunucu belgeyi kapatabilirsiniz.  
  
 Windows SDK'ın bkz `IUnknown::AddRef` ve `IUnknown::Release`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Otomasyon sunucuları](../mfc/automation-servers.md)   
 [AfxOleCanExitApp](../mfc/reference/application-control.md#afxolecanexitapp)

