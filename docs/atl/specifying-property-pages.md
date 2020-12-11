---
description: 'Daha fazla bilgi edinin: özellik sayfalarını belirtme'
title: Özellik sayfalarını belirtme (ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- ISpecifyPropertyPages method
- property pages, specifying
ms.assetid: ee8678cf-c708-49ab-b0ad-fc2db31f1ac3
ms.openlocfilehash: 171440dde11178c85d1f636874b0b161691cb9cc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97157431"
---
# <a name="specifying-property-pages"></a>Özellik sayfalarını belirtme

Bir ActiveX denetimi oluşturduğunuzda, genellikle bu dosyayı denetiminizin özelliklerini ayarlamak için kullanılabilecek özellik sayfaları ile ilişkilendirmeniz gerekir. Denetim kapsayıcıları, `ISpecifyPropertyPages` denetimin özelliklerini ayarlamak için hangi özellik sayfalarının kullanılabileceğini bulmak için arabirimini kullanır. Bu arabirimi, denetiinize uygulamanız gerekir.

`ISpecifyPropertyPages`ATL kullanarak uygulamak için aşağıdaki adımları uygulayın:

1. [Idiifyıpropertypagesimpl](../atl/reference/ispecifypropertypagesimpl-class.md)' den sınıfınızı türetebilirsiniz.

1. Sınıfınızın COM eşlemesine için bir giriş ekleyin `ISpecifyPropertyPages` .

1. Denetiminizin ilişkilendirildiği her sayfa için özellik eşlemesine bir [PROP_PAGE](reference/property-map-macros.md#prop_page) girişi ekleyin.

> [!NOTE]
> [Atl Denetim Sihirbazı](../atl/reference/atl-control-wizard.md)kullanılarak standart bir denetim oluştururken, yalnızca PROP_PAGE girdilerini özellik eşlemesine eklemeniz gerekir. Sihirbaz, diğer adımlar için gerekli kodu oluşturur.

İyi davranmış kapsayıcılar, belirtilen özellik sayfalarını Özellik eşlemesindeki PROP_PAGE girişleriyle aynı sırada görüntüler. Genellikle, kullanıcıların denetime özgü sayfaları görebilmesi için, standart özellik sayfası girdilerini Özellik eşlemesindeki özel sayfalarınıza ait girdilerden sonra koymanız gerekir.

## <a name="example"></a>Örnek

Bir takvim denetimine yönelik aşağıdaki sınıf, `ISpecifyPropertyPages` kendi özelliklerinin özel bir tarih sayfası ve hisse senedi rengi sayfası kullanılarak ayarlanbilicinize söylemek için arabirimini kullanır.

[!code-cpp[NVC_ATL_Windowing#72](../atl/codesnippet/cpp/specifying-property-pages_1.h)]

## <a name="see-also"></a>Ayrıca bkz.

[Özellik Sayfaları](../atl/atl-com-property-pages.md)<br/>
[ATLPages örneği](../overview/visual-cpp-samples.md)
