---
title: ATL pencere özelliklerini | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- window traits
ms.assetid: c90cf850-9e91-49da-9cf3-ad4efb30347d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 28336cca8c9dbd808b28575569b7f2bddf97ec58
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/05/2018
ms.locfileid: "37851274"
---
# <a name="understanding-window-traits"></a>Pencere özelliklerini anlama
Pencere özellikler sınıfları bir ATL pencere nesnesi oluşturmak için kullanılan stilleri Standartlaştırma için basit bir yöntem sağlar. Pencere özelliklerini şablon parametreleri olarak kabul edilir [Cwindowımpl](../atl/reference/cwindowimpl-class.md) ve diğer sınıf düzeyinde pencere stilleri varsayılan sağlamanın bir yolu olarak ATL pencere sınıfları.  
  
 Bir pencere örneği oluşturan çağrısı açıkça stillerde sağlamıyorsa [Oluştur](../atl/reference/cwindowimpl-class.md#create), pencerenin hala doğru stilleri ile oluşturulan emin olmak için nitelikler sınıfı kullanabilirsiniz. Bile belirli stilleri o pencereyi sınıfın tüm örnekleri için diğer stilleri kullanılmasına da izin veren bir örneği başına temelinde ayarlamak için ayarlandığından emin olun.  
  
## <a name="atl-window-traits-templates"></a>ATL pencere nitelikler şablonları  
 ATL, kendi şablon parametrelerini kullanarak derleme zamanında varsayılan stillerini ayarlamanıza olanak sağlayan iki penceresi nitelikler şablonları sağlar.  
  
|örneği|Açıklama|  
|-----------|-----------------|  
|[CWinTraits](../atl/reference/cwintraits-class.md)|Diğer bir stilleri çağrısında belirtildiğinde, kullanılacak pencere stilleri varsayılan sağlamak istediğinizde bu şablonu kullanın `Create`. Derleme zamanı sırasında çalışma zamanı önceliklidir ayarlanan stilleri üzerinden sağlanan stilleri.|  
|[CWinTraitsOR](../atl/reference/cwintraitsor-class.md)|Bu sınıf, her zaman için pencere sınıfını ayarlanmalıdır stilleri belirtmek istediğinizde kullanın. Çalışma zamanında sağlanan stilleri, bit düzeyinde OR işleci kullanılarak derleme zamanında ayarlama stilleri ile birleştirilir.|  
  
 Bu şablonlara ek olarak, ATL önceden tanımlanmış uzmanlıkları sayısını sağlar. `CWinTraits` pencere stilleri yaygın olarak kullanılan birleşimleri için şablon. Bkz: [CWinTraits](../atl/reference/cwintraits-class.md) başvuru tüm ayrıntılar için belgeleri.  
  
## <a name="custom-window-traits"></a>Özel pencere özelliklerini  
 ATL tarafından sağlanan şablonları özelleştirilmiş birinin olası durumda yeterli olmadığından ve kendi nitelikler sınıfı oluşturmak için ihtiyacınız, iki statik işlevler uygulayan bir sınıf oluşturmak yeterlidir: `GetWndStyle` ve `GetWndStyleEx`:  
  
 [!code-cpp[NVC_ATL_Windowing#68](../atl/codesnippet/cpp/understanding-window-traits_1.h)]  
  
 Bu işlevlerin her biri bazı stil değeri yeni bir stil değer oluşturmak için kullanabileceğiniz çalışma zamanında geçirilir. Pencere nitelikler sınıfınızın bir ATL pencere sınıfı için şablon bağımsız değişkeni olarak kullanılıyorsa, bu statik işlevlere geçirilen stil değerleri ne olursa olsun stil bağımsız değişken olarak geçirilen olacaktır [Oluştur](../atl/reference/cwindowimpl-class.md#create).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Pencere sınıfları](../atl/atl-window-classes.md)

