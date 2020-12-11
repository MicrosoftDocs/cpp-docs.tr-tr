---
description: 'Daha fazla bilgi edinin: pencere niteliklerini anlama'
title: ATL penceresi nitelikleri
ms.date: 11/04/2016
helpviewer_keywords:
- window traits
ms.assetid: c90cf850-9e91-49da-9cf3-ad4efb30347d
ms.openlocfilehash: a42ef66afe09e0e528f05419799dce48c43b1bbf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97157301"
---
# <a name="understanding-window-traits"></a>Pencere niteliklerini anlama

Pencere nitelikleri sınıfları, ATL pencere nesnesi oluşturmak için kullanılan stilleri standartlaştırarak basit bir yöntem sağlar. Pencere nitelikleri, sınıf düzeyinde varsayılan pencere stilleri sağlamanın bir yolu olarak [CWindowImpl](../atl/reference/cwindowimpl-class.md) ve diğer atl pencere sınıfları tarafından şablon parametreleri olarak kabul edilir.

Bir pencere örneğinin Oluşturucusu, [oluşturma](../atl/reference/cwindowimpl-class.md#create)çağrısında açıkça stil sağlamıyorsa, pencerenin doğru stillerle oluşturulduğundan emin olmak için bir nitelikler sınıfı kullanabilirsiniz. Diğer stillerin örnek temelinde ayarlanmaya izin verirken, belirli stillerin bu pencere sınıfının tüm örnekleri için ayarlanmış olmasına de dikkat edin.

## <a name="atl-window-traits-templates"></a>ATL pencere nitelikleri şablonları

ATL, şablon parametrelerini kullanarak derleme zamanında varsayılan stilleri ayarlamanıza olanak tanıyan iki pencere nitelikleri şablonu sağlar.

|Sınıf|Açıklama|
|-----------|-----------------|
|[CWinTraits](../atl/reference/cwintraits-class.md)|Çağrıda yalnızca başka bir stil belirtilmediğinde kullanılacak varsayılan pencere stilleri sağlamak istediğinizde bu şablonu kullanın `Create` . Çalışma zamanında belirtilen stiller, derleme zamanında ayarlanan stillerdeki önceliğe sahip olur.|
|[CWinTraitsOR](../atl/reference/cwintraitsor-class.md)|Pencere sınıfı için her zaman ayarlanması gereken stilleri belirtmek istediğinizde bu sınıfı kullanın. Çalışma zamanında belirtilen stiller, bit düzeyinde OR işleci kullanılarak derleme zamanında ayarlanan stillerle birleştirilir.|

Bu şablonların yanı sıra, ATL, `CWinTraits` pencere stillerinin yaygın olarak kullanılan birleşimleri için şablon için önceden tanımlanmış birçok özelleştirilmiş öğe sağlar. Tüm ayrıntılar için [CWinTraits](../atl/reference/cwintraits-class.md) başvuru belgelerine bakın.

## <a name="custom-window-traits"></a>Özel pencere nitelikleri

ATL tarafından sunulan şablonlardan birini özelleştirmenin yeterli olmaması durumunda ve kendi nitelikler sınıfınızı oluşturmanız gerekiyorsa, yalnızca iki statik işlevi uygulayan bir sınıf oluşturmanız gerekir: `GetWndStyle` ve `GetWndStyleEx` :

[!code-cpp[NVC_ATL_Windowing#68](../atl/codesnippet/cpp/understanding-window-traits_1.h)]

Bu işlevlerin her biri, yeni bir stil değeri oluşturmak için kullanabileceği çalışma zamanında bazı stil değerlerini geçirilecek. Pencere nitelikleri sınıfınız bir ATL pencere sınıfına şablon bağımsız değişkeni olarak kullanılıyorsa, bu statik işlevlere geçirilen stil değerleri, [oluşturulacak](../atl/reference/cwindowimpl-class.md#create)stil bağımsız değişkenleri olarak geçirilir.

## <a name="see-also"></a>Ayrıca bkz.

[Pencere sınıfları](../atl/atl-window-classes.md)
