---
title: ATL COM özellik sayfaları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- property pages, COM
- ATL COM objects
- COM property pages
- property pages, ATL
- COM objects, ATL
- ATL property pages
ms.assetid: 663c7caa-2e5e-4b5c-b8ea-fd434ceb1654
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3fdf0d53cca00424c2c933e2578fb5c70b7d07e1
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/14/2018
ms.locfileid: "42464774"
---
# <a name="atl-com-property-pages"></a>ATL COM Özellik Sayfaları
COM özellik sayfaları, özellikleri ayarlamak için bir kullanıcı arabirimi sağlar (veya çağırma yöntemleri) bir veya daha fazla COM nesneleri. Özellik sayfaları, denetim özelliklerini tasarım zamanında ayarlanacak sağlayan zengin kullanıcı arabirimleri sağlamak için ActiveX denetimleri tarafından yaygın olarak kullanılır.  
  
 Özellik sayfaları olan COM nesneleri uygulayan [IPropertyPage](http://msdn.microsoft.com/library/windows/desktop/ms691246) veya [IPropertyPage2](http://msdn.microsoft.com/library/windows/desktop/ms683996) arabirimi. Bu arabirimleri ile ilişkilendirilmesi için sayfayı sağlayan yöntemler sunar bir `site` (sayfanın kapsayıcıyı temsil eden bir COM nesnesi) ve bir dizi *nesneleri* (yöntemleri değişikliklere yanıt olarak çağrılacağı COM nesneleri özellik sayfasının kullanıcı tarafından yapılan). Özellik sayfası kapsayıcı sayfası kullanıcı arabirimi ve değişikliklerin uygulanması ne zaman göstermek veya gizlemek için temel nesneler için kullanıcı tarafından yapılan bildirebilen için özellik sayfası arabirimindeki yöntemleri çağırmak için sorumludur.  
  
 Her bir özellik sayfası tamamen özellikleri ayarlanabilir nesneleri bağımsız olarak oluşturulabilir. Tüm bu özellik sayfası ihtiyaçlarını belirli bir arabirim (veya arabirimleri kümesi) anlamak için bu arabirimdeki yöntemleri çağırmak için bir kullanıcı arabirim sağlamak üzere olduğundan.  
  
 Daha fazla bilgi için [özellik bölümleri ve özellik sayfaları](http://msdn.microsoft.com/library/windows/desktop/ms686577) Windows SDK.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Özellik Sayfaları Belirtme](../atl/specifying-property-pages.md)  
 Özellik sayfaları, denetim için belirtmek için adımları ve örnek bir sınıf gösterir.  
  
 [Özellik Sayfaları Uygulama](../atl/implementing-property-pages.md)  
 Özellik sayfaları, geçersiz kılmak için yöntemleri dahil olmak üzere uygulamaya yönelik adımlar listelenmektedir. ATLPages örnek programına dayalı tam bir örnek gösterilmektedir.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [ATLPages örnek](../visual-cpp-samples.md)  
 Örnek özet kullanarak bir özellik sayfası uygulayan ATLPages örnek `IPropertyPageImpl`.  
  
 [ATL](../atl/active-template-library-atl-concepts.md)  
 Active Template Library kullanarak programlama hakkında kavramsal konulara bağlantılar sağlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kavramları](../atl/active-template-library-atl-concepts.md)

