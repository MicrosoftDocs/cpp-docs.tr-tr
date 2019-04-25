---
title: ATL pencere özelliklerini
ms.date: 11/04/2016
helpviewer_keywords:
- window traits
ms.assetid: c90cf850-9e91-49da-9cf3-ad4efb30347d
ms.openlocfilehash: 29549e54051405fc3dd4d5d7ae70a382ad7a62ea
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62196189"
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

## <a name="see-also"></a>Ayrıca bkz.

[Pencere sınıfları](../atl/atl-window-classes.md)
