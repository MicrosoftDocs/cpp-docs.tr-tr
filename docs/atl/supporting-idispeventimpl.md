---
title: Idispeventımpl destekleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- IDispEventImpl
dev_langs:
- C++
helpviewer_keywords:
- event sink maps, declaring
- IDispEventImpl class, advising and unadvising
- SINK_ENTRY macro
- type libraries, importing
- ATL, IDispEventImpl support in COM objects
- BEGIN_SINK_MAP macro
- IDispEventImpl class, declaring
ms.assetid: b957f930-6a5b-4598-8e4d-8027759957e7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7d7bfd2690cf8f1ed692e6e21bf05b56e2280ce0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46055669"
---
# <a name="supporting-idispeventimpl"></a>Idispeventımpl destekleme

Şablon sınıfı [Idispeventımpl](../atl/reference/idispeventimpl-class.md) ATL sınıfınızdaki bağlantı noktası havuzlar için destek sağlamak için kullanılabilir. Bir bağlantı noktası havuzu, dış COM nesneleri tetiklenen olayı işlemek kendi sınıfınızı sağlar. Bu bağlantı noktası havuzlarını, sınıfı tarafından sağlanan bir olay havuzu Haritası ile eşlenir.

Sınıfınız için bir bağlantı noktası havuzu düzgün bir şekilde uygulamak için aşağıdaki adımlar tamamlanmalıdır:

- Dış her nesne için tür kitaplıklarını içeri aktarma

- Bildirme `IDispEventImpl` arabirimleri

- Bir olay havuzu eşlemesi bildirme

- Öneri ve bağlantı noktalarını eşlemesindeki

Bir bağlantı noktası havuzu uygulamada yer alan adımların tümünü yalnızca üst bilgi dosyası (.h) sınıfınızın değiştirerek gerçekleştirilebilir.

## <a name="importing-the-type-libraries"></a>Tür kitaplıklarını içeri aktarma

Olayları işlemek istediğiniz her dış nesne için tür kitaplığı içeri aktarmanız gerekir. Bu adım, işlenebilir olayları tanımlar ve olay havuzu eşlemesi bildirilirken kullanılır bilgi sağlar. [#İmport](../preprocessor/hash-import-directive-cpp.md) yönergesi, bunu gerçekleştirmek için kullanılabilir. Gerekli Ekle `#import` yönerge satır sınıfınız için üst bilgi dosyası (.h) destekleyeceği her gönderme arabirimi.

Aşağıdaki örnek, bir dış COM sunucusunun tür kitaplığı içeri aktarır (`MSCAL.Calendar.7`):

[!code-cpp[NVC_ATL_Windowing#141](../atl/codesnippet/cpp/supporting-idispeventimpl_1.h)]

> [!NOTE]
>  Ayrı bir olmalıdır `#import` deyimi tarafından destekleneceğinden her dış tür kitaplığı için.

## <a name="declaring-the-idispeventimpl-interfaces"></a>Idispeventımpl arabirimleri bildirme

Her gönderme arabiriminin tür kitaplıklarını içeri aktardığınız, ayrı bildirmenize gerek `IDispEventImpl` arabirimler için her bir dış gönderme arabirimi. Ekleyerek, sınıfının bildirimi değiştirin bir `IDispEventImpl` bildirimi dış her nesne için arabirim. Parametreler hakkında daha fazla bilgi için bkz. [Idispeventımpl](../atl/reference/idispeventimpl-class.md).

Aşağıdaki kod, için iki bağlantı noktası havuzlarını bildirir `DCalendarEvents` arabirimi, sınıf tarafından uygulanan COM nesnesinin `CMyCompositCtrl2`:

[!code-cpp[NVC_ATL_Windowing#142](../atl/codesnippet/cpp/supporting-idispeventimpl_2.h)]

## <a name="declaring-an-event-sink-map"></a>Bir olay havuzu eşlemesi bildirme

Uygun işlevi tarafından işlenecek olay bildirimleri, sınıfınıza doğru işleyicisine her bir olay yönlendirme gerekir. Bu, bir olay havuzu eşlemesi bildirerek sağlanır.

ATL sağlayan çeşitli makrolar [BEGIN_SINK_MAP](reference/composite-control-macros.md#begin_sink_map), [END_SINK_MAP](reference/composite-control-macros.md#end_sink_map), ve [SINK_ENTRY_EX](reference/composite-control-macros.md#sink_entry_ex), oluşturan bu eşlemeyi daha kolay. Standart biçim şu şekildedir:

```cpp
BEGIN_SINK_MAP(comClass)
  SINK_ENTRY_EX(id, iid, dispid, func)
  . . . //additional external event entries
END_SINK_MAP()
```

Aşağıdaki örnek, bir olay havuzu eşlemesi ile iki olay işleyicileri bildirir:

[!code-cpp[NVC_ATL_Windowing#136](../atl/codesnippet/cpp/supporting-idispeventimpl_3.h)]

Neredeyse tamamlandı uygulamasıdır. Son adım advising ve dış arabirimlerin unadvising ilgilidir.

## <a name="advising-and-unadvising-the-idispeventimpl-interfaces"></a>Bildiren ve Unadvising Idispeventımpl arabirimleri

Son adım, uygun zamanlarda bildirmek (eşlemesindeki tüm bağlantı noktaları veya kuracağınız) bir yöntem uygulamaktır. Dış istemcilerle nesnenizin arasındaki iletişim yapılabilmesi bu bildiren yapılmalıdır. Nesnenizin görünür hale gelmesi önce nesne tarafından desteklenen her bir dış gönderme arabirimi giden arabirimler için sorgulanır. Bir bağlantı kurulur ve giden arabirimine bir başvuru nesneden olayları işlemek için kullanılır. Bu yordamı "bildiren olarak." olarak adlandırılır

Nesnenizin ile dış arabirimler tamamlandıktan sonra giden arabirimleri bunlar artık, sınıfı tarafından kullanılır açamayacakları bildirilmelidir. Bu işlem "unadvising olarak." olarak adlandırılır

COM nesnelerinin benzersiz yapısı nedeniyle, bu yordamı, ayrıntı ve yürütme, uygulamalar arasında değişir. Bu ayrıntılar, bu konunun kapsamı dışındadır ve ele alınmayan.

## <a name="see-also"></a>Ayrıca Bkz.

[ATL COM Nesnelerinin Temelleri](../atl/fundamentals-of-atl-com-objects.md)

