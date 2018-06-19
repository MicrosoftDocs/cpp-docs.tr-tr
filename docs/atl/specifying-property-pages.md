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
ms.openlocfilehash: e8d4cbeaa8ea9a57f9287f2d2fe78c61884ba4a3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32358931"
---
# <a name="specifying-property-pages"></a>Özellik sayfaları belirtme
ActiveX denetimi oluşturduğunuzda, genellikle denetim özelliklerini ayarlamak için kullanılan özellik sayfaları ile ilişkilendirmek isteyeceksiniz. Denetim kapsayıcıları kullanma **ISpecifyPropertyPages** hangi özellik sayfaları denetiminizin özelliklerini ayarlamak için kullanılabilir çıkışı bulmak için arabirim. Denetiminizde bu arabirimini uygulaması gerekir.  
  
 Uygulanacak **ISpecifyPropertyPages** ATL, kullanarak aşağıdaki adımları gerçekleştirin:  
  
1.  Sınıfından türetilen [ISpecifyPropertyPagesImpl](../atl/reference/ispecifypropertypagesimpl-class.md).  
  
2.  İçin bir giriş eklemek **ISpecifyPropertyPages** sınıfınızın COM eşlemesi için.  
  
3.  Ekleme bir [PROP_PAGE](reference/property-map-macros.md#prop_page) denetimi ile ilişkilendirilmiş her bir sayfa için özellik eşlemesi girişe.  
  
> [!NOTE]
>  Standart denetimini kullanarak oluştururken [ATL Denetim Sihirbazı](../atl/reference/atl-control-wizard.md), yalnızca eklemeniz gerekecektir `PROP_PAGE` özellik eşlemesi girişlere. Sihirbazın diğer adımlar için gerekli kod oluşturur.  
  
 Uyum gösteren kapsayıcıları görüntüler belirtilen özellik sayfaları aynı sırada `PROP_PAGE` girişleri özellik eşlemesi. Böylece kullanıcılar ilk denetiminize belirli sayfalara bakın genel olarak, standart özellik sayfası girişleri sonra girişleri özel sayfalarınızda özellik eşlemesi için moduna geçirmelisiniz.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki sınıf bir takvim için kullandığı kontrol **ISpecifyPropertyPages** arabirimi özelliklerini özel tarih sayfası ve stok renk sayfası kullanılarak ayarlanabilir kapsayıcıları söyleyin.  
  
 [!code-cpp[NVC_ATL_Windowing#72](../atl/codesnippet/cpp/specifying-property-pages_1.h)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özellik sayfaları](../atl/atl-com-property-pages.md)   
 [ATLPages örnek](../visual-cpp-samples.md)

