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
ms.openlocfilehash: d5d7904b9f31a1be858dadaa8a087c720c277465
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32357538"
---
# <a name="atl-com-property-pages"></a>ATL COM Özellik Sayfaları
COM özellik sayfaları özelliklerini ayarlamak için bir kullanıcı arabirimi sağlar (veya yöntemleri çağırma) bir veya daha fazla COM Nesne. Özellik sayfaları, tasarım zamanında ayarlanacak denetim özellikleri sağlayan zengin bir kullanıcı arabirimleri sağlamak için ActiveX denetimleri tarafından yaygın olarak kullanılır.  
  
 Özellik sayfaları olan COM nesneleri uygulayan [IPropertyPage](http://msdn.microsoft.com/library/windows/desktop/ms691246) veya [IPropertyPage2](http://msdn.microsoft.com/library/windows/desktop/ms683996) arabirimi. Bu arabirimleri ile ilişkili sayfanın izin yöntemleri sunar bir `site` (sayfanın kapsayıcısını temsil eden bir COM nesnesi) ve bir dizi *nesneleri* (değişikliklere yanıt olan yöntemleri çağrılır COM nesneleri özellik sayfası kullanıcı tarafından yapılan). Özellik sayfası kapsayıcı, kendi kullanıcı arabirimi ve değişiklikleri uygulamak ne zaman göstermek veya gizlemek için temel nesnelere kullanıcı tarafından yapıldığında sayfa bildirmek için özellik sayfası arabirimde yöntemleri çağırmak için sorumludur.  
  
 Her özellik sayfası tamamen özellikleri ayarlanabilir nesneleri bağımsız olarak oluşturulabilir. Tüm bu özellik sayfası ihtiyaçlarını belirli bir arabirim (veya arabirimleri) anlamak için bu arabirimdeki yöntemleri çağırmak için bir kullanıcı arabirimi sağlamak için ise.  
  
 Daha fazla bilgi için bkz: [özellik bölümleri ve özellik sayfaları](http://msdn.microsoft.com/library/windows/desktop/ms686577) içinde [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Özellik Sayfaları Belirtme](../atl/specifying-property-pages.md)  
 Özellik sayfaları, denetim için belirtmek için adımları listeler ve örnek bir sınıf gösterir.  
  
 [Özellik Sayfaları Uygulama](../atl/implementing-property-pages.md)  
 Özellik sayfaları, geçersiz kılmak için yöntemleri de dahil olmak üzere uygulamaya yönelik adımlar listelenmektedir. ATLPages örnek programı temel alarak tam bir örnek size yol göstermektedir.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [ATLPages örnek](../visual-cpp-samples.md)  
 Özellik sayfası kullanılarak uygulayan ATLPages örnek örnek Özet `IPropertyPageImpl`.  
  
 [ATL](../atl/active-template-library-atl-concepts.md)  
 Etkin Şablon Kütüphanesi kullanarak programı kavramsal konulara bağlantılar verilmektedir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kavramları](../atl/active-template-library-atl-concepts.md)

