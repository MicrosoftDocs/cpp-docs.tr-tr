---
title: ATL COM Özellik Sayfaları
ms.date: 11/04/2016
helpviewer_keywords:
- property pages, COM
- ATL COM objects
- COM property pages
- property pages, ATL
- COM objects, ATL
- ATL property pages
ms.assetid: 663c7caa-2e5e-4b5c-b8ea-fd434ceb1654
ms.openlocfilehash: d374569c6c3e9bb63b6b026d2b0f86226d158f36
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62252461"
---
# <a name="atl-com-property-pages"></a>ATL COM Özellik Sayfaları

COM özellik sayfaları, özellikleri ayarlamak için bir kullanıcı arabirimi sağlar (veya çağırma yöntemleri) bir veya daha fazla COM nesneleri. Özellik sayfaları, denetim özelliklerini tasarım zamanında ayarlanacak sağlayan zengin kullanıcı arabirimleri sağlamak için ActiveX denetimleri tarafından yaygın olarak kullanılır.

Özellik sayfaları olan COM nesneleri uygulayan [IPropertyPage](/windows/desktop/api/ocidl/nn-ocidl-ipropertypage) veya [IPropertyPage2](/windows/desktop/api/ocidl/nn-ocidl-ipropertypage2) arabirimi. Bu arabirimleri ile ilişkilendirilmesi için sayfayı sağlayan yöntemler sunar bir `site` (sayfanın kapsayıcıyı temsil eden bir COM nesnesi) ve bir dizi *nesneleri* (yöntemleri değişikliklere yanıt olarak çağrılacağı COM nesneleri özellik sayfasının kullanıcı tarafından yapılan). Özellik sayfası kapsayıcı sayfası kullanıcı arabirimi ve değişikliklerin uygulanması ne zaman göstermek veya gizlemek için temel nesneler için kullanıcı tarafından yapılan bildirebilen için özellik sayfası arabirimindeki yöntemleri çağırmak için sorumludur.

Her bir özellik sayfası tamamen özellikleri ayarlanabilir nesneleri bağımsız olarak oluşturulabilir. Tüm bu özellik sayfası ihtiyaçlarını belirli bir arabirim (veya arabirimleri kümesi) anlamak için bu arabirimdeki yöntemleri çağırmak için bir kullanıcı arabirim sağlamak üzere olduğundan.

Daha fazla bilgi için [özellik bölümleri ve özellik sayfaları](/windows/desktop/com/property-sheets-and-property-pages) Windows SDK.

## <a name="in-this-section"></a>Bu Bölümde

[Özellik Sayfaları Belirtme](../atl/specifying-property-pages.md)<br/>
Özellik sayfaları, denetim için belirtmek için adımları ve örnek bir sınıf gösterir.

[Özellik Sayfaları Uygulama](../atl/implementing-property-pages.md)<br/>
Özellik sayfaları, geçersiz kılmak için yöntemleri dahil olmak üzere uygulamaya yönelik adımlar listelenmektedir. ATLPages örnek programına dayalı tam bir örnek gösterilmektedir.

## <a name="related-sections"></a>İlgili Bölümler

[ATLPages örnek](../overview/visual-cpp-samples.md)<br/>
Örnek özet kullanarak bir özellik sayfası uygulayan ATLPages örnek `IPropertyPageImpl`.

[ATL](../atl/active-template-library-atl-concepts.md)<br/>
Active Template Library kullanarak programlama hakkında kavramsal konulara bağlantılar sağlar.

## <a name="see-also"></a>Ayrıca bkz.

[Kavramları](../atl/active-template-library-atl-concepts.md)
