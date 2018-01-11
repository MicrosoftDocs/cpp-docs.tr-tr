---
title: ATL pencere nitelikler | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: window traits
ms.assetid: c90cf850-9e91-49da-9cf3-ad4efb30347d
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fda95e4517d2717a89310a8e49a0c5b337feebcf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="understanding-window-traits"></a>Pencere özellikleri anlama
Pencere özellikler sınıfları ATL pencere nesnesi oluşturmak için kullanılan stiller Standartlaştırma için basit bir yöntem sağlar. Pencere özellikleri şablonu parametreleri olarak kabul edilir [CWindowImpl](../atl/reference/cwindowimpl-class.md) ve diğer ATL pencere sınıfları sınıf düzeyinde pencere stilleri varsayılan sağlamanın bir yolu olarak.  
  
 Bir pencere örneği oluşturan çağrısı açıkça stillerde sağlamıyorsa [oluşturma](../atl/reference/cwindowimpl-class.md#create), pencerenin hala doğru stilleri ile oluşturulan emin olmak için nitelikler sınıfını kullanabilirsiniz. Bile belirli stilleri Bu pencere sınıfın tüm örnekleri için diğer stilleri izin veren bir örneği başına temelinde ayarlanacak ayarlandığından emin olun.  
  
## <a name="atl-window-traits-templates"></a>ATL pencere nitelikler şablonları  
 ATL varsayılan stillerini şablon parametrelerini kullanarak derleme zamanında ayarlamanıza izin iki penceresi nitelikler şablonları sağlar.  
  
|örneği|Açıklama|  
|-----------|-----------------|  
|[CWinTraits](../atl/reference/cwintraits-class.md)|Diğer bir stilleri çağrısında belirtildiğinde, kullanılacak pencere stilleri varsayılan sağlamak istediğinizde bu şablonu kullanmak **oluşturma**. Derleme zamanı sırasında çalışma zamanı önceliklidir belirlenmiş stilleri üzerinden sağlanan stilleri.|  
|[CWinTraitsOR](../atl/reference/cwintraitsor-class.md)|Pencere sınıfı için her zaman ayarlanmalıdır stilleri belirtmek istediğinizde bu sınıfı kullanın. Çalışma zamanında sağlanan stilleri bit düzeyinde OR işleci kullanılarak derleme zamanında stiline ile birleştirilir.|  
  
 Bu şablonlar ek olarak önceden tanımlanmış özelleştirmeleri birkaç ATL sağlar `CWinTraits` pencere stilleri yaygın olarak kullanılan bileşimleri için şablon. Bkz: [CWinTraits](../atl/reference/cwintraits-class.md) başvuru belgelerini tam Ayrıntılar için.  
  
## <a name="custom-window-traits"></a>Özel pencere özellikleri  
 Olası durumda özelleştirilmiş bir ATL tarafından sağlanan şablonları yeterli değilse ve kendi nitelikler sınıfı oluşturmanız gerekir, iki statik işlevler uygulayan bir sınıf oluşturmak yeterlidir: `GetWndStyle` ve **GetWndStyleEx** :  
  
 [!code-cpp[NVC_ATL_Windowing#68](../atl/codesnippet/cpp/understanding-window-traits_1.h)]  
  
 Bu işlevlerin her biri bazı stil değeri yeni stil değer oluşturmak üzere kullanabileceğiniz çalışma zamanında geçirilir. Pencere özellikleri sınıfı ATL pencere sınıfı şablon bağımsız değişken olarak kullanılıyorsa, bu statik, işlevlere geçirilen stili değerler ne olursa olsun stil bağımsız değişken olarak geçirilen olacaktır [oluşturma](../atl/reference/cwindowimpl-class.md#create).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Pencere sınıfları](../atl/atl-window-classes.md)

