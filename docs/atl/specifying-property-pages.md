---
title: Özellik sayfaları (ATL) belirtme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- ISpecifyPropertyPages
dev_langs:
- C++
helpviewer_keywords:
- ISpecifyPropertyPages method
- property pages, specifying
ms.assetid: ee8678cf-c708-49ab-b0ad-fc2db31f1ac3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f80abd3b6270f105fecd7ef8b9988a379901b541
ms.sourcegitcommit: 997e6b7d336cddb388bb6e9e56527725fcaa0624
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/08/2018
ms.locfileid: "48860218"
---
# <a name="specifying-property-pages"></a>Özellik sayfaları belirtme

ActiveX denetimi oluşturduğunuzda, genellikle, denetimin özelliklerini ayarlamak için kullanılan özellik sayfaları ile ilişkilendirilecek isteyeceksiniz. Denetim kapsayıcılar kullanım `ISpecifyPropertyPages` hangi özellik sayfaları denetimin özelliklerini ayarlamak için kullanılan çıkış bulmak için arabirim. Denetiminizi bu arabirimi uygulayan gerekecektir.

Uygulamak için `ISpecifyPropertyPages` ATL, kullanarak aşağıdaki adımları atın:

1. Öğesinden, bir sınıf türetin [Ispecifypropertypagesımpl](../atl/reference/ispecifypropertypagesimpl-class.md).

1. Bir girdi ekleyin `ISpecifyPropertyPages` sınıfınızın COM eşlemesine.

1. Ekleme bir [PROP_PAGE](reference/property-map-macros.md#prop_page) , denetimle ilişkili her sayfa için özellik eşleme girişi.

> [!NOTE]
> Kullanarak bir standart denetim oluştururken [ATL denetimi Sihirbazı](../atl/reference/atl-control-wizard.md), yalnızca PROP_PAGE girişleri için özellik eşlemesi eklemeniz gerekir. Sihirbazın diğer adımlar için gerekli kodu oluşturur.

Uyum gösteren kapsayıcıları aynı sırada özellik eşlemesi PROP_PAGE girişleri olarak belirtilen özellik sayfalarını görüntüler. Böylece kullanıcı denetiminiz için belirli sayfalara ilk bakın genellikle, standart özellik sayfa girdileri girişleri sonra özel sayfalarınızı özellik eşlemesi için koymanız gerekir.

## <a name="example"></a>Örnek

Şu sınıf için bir Takvim denetimi kullanan `ISpecifyPropertyPages` özelliklerini, özel tarih sayfası ve rengi stok sayfası kullanılarak ayarlanabilir kapsayıcıları bildirmek için arabirim.

[!code-cpp[NVC_ATL_Windowing#72](../atl/codesnippet/cpp/specifying-property-pages_1.h)]

## <a name="see-also"></a>Ayrıca Bkz.

[Özellik Sayfaları](../atl/atl-com-property-pages.md)<br/>
[ATLPages örnek](../visual-cpp-samples.md)
