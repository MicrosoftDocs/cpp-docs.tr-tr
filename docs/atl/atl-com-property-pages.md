---
description: 'Daha fazla bilgi edinin: ATL COM özellik sayfaları'
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
ms.openlocfilehash: 252e8a98f4f34a07a374c77fc48aacd7eee8969f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97165985"
---
# <a name="atl-com-property-pages"></a>ATL COM Özellik Sayfaları

COM özellik sayfaları bir veya daha fazla COM nesnesinin özelliklerini ayarlamak için bir kullanıcı arabirimi sağlar. Özellik sayfaları, denetim özelliklerinin tasarım zamanında ayarlamaya izin veren zengin Kullanıcı arabirimleri sağlamak için ActiveX denetimleri tarafından kapsamlı olarak kullanılır.

Özellik sayfaları, [IPropertyPage](/windows/win32/api/ocidl/nn-ocidl-ipropertypage) veya [IPROPERTYPAGE2](/windows/win32/api/ocidl/nn-ocidl-ipropertypage2) arabirimini uygulayan com nesneleridir. Bu arabirimler, sayfanın bir `site` (sayfanın kapsayıcısını temsil eden BIR com nesnesi) ve bir dizi *nesne* (özellik sayfası kullanıcı tarafından yapılan değişikliklere yanıt olarak çağrılacak com nesneleri) ile ilişkilendirilmesine izin veren yöntemler sağlar. Özellik sayfası kapsayıcısı, sayfanın Kullanıcı arabirimini gösterip göstermeyeceğini ve Kullanıcı tarafından hangi değişikliklerin temel alınan nesnelere ne zaman uygulanacağını söylemek için özellik sayfası arabirimindeki yöntemlerin çağrılmasından sorumludur.

Her özellik sayfası, özelliklerinin ayarlananındaki nesnelerden tamamen bağımsız şekilde oluşturulabilir. Tüm özellik sayfaları, belirli bir arabirimi (veya arabirim kümesini) anlamaktır ve bu arabirimdeki yöntemleri çağırmak için bir kullanıcı arabirimi sağlar.

Daha fazla bilgi için Windows SDK [Özellik sayfaları ve özellik sayfaları](/windows/win32/com/property-sheets-and-property-pages) bölümüne bakın.

## <a name="in-this-section"></a>Bu Bölümde

[Özellik sayfalarını belirtme](../atl/specifying-property-pages.md)<br/>
Denetiminizin özellik sayfalarını belirtme adımlarını listeler ve örnek bir sınıfı gösterir.

[Özellik sayfalarını uygulama](../atl/implementing-property-pages.md)<br/>
Geçersiz kılınacak yöntemler de dahil olmak üzere özellik sayfalarını uygulamaya yönelik adımları listeler. ATLPages örnek programına dayalı olarak size bir örnek sağlar.

## <a name="related-sections"></a>İlgili Bölümler

[ATLPages örneği](../overview/visual-cpp-samples.md)<br/>
Kullanarak bir özellik sayfası uygulayan, ATLPages örneği için örnek Özet `IPropertyPageImpl` .

[ATL](../atl/active-template-library-atl-concepts.md)<br/>
Etkin Şablon kitaplığı 'nı kullanarak programla programlama hakkında kavramsal konuların bağlantılarını sağlar.

## <a name="see-also"></a>Ayrıca bkz.

[Kavramlar](../atl/active-template-library-atl-concepts.md)
