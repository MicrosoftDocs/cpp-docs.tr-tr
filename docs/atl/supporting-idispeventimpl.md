---
description: "Daha fazla bilgi edinin: IDispEventImpl 'yi destekleme"
title: IDispEventImpl desteği
ms.date: 11/04/2016
helpviewer_keywords:
- event sink maps, declaring
- IDispEventImpl class, advising and unadvising
- SINK_ENTRY macro
- type libraries, importing
- ATL, IDispEventImpl support in COM objects
- BEGIN_SINK_MAP macro
- IDispEventImpl class, declaring
ms.assetid: b957f930-6a5b-4598-8e4d-8027759957e7
ms.openlocfilehash: 6a5c12e011ad0dc0f27594325a22dadddd5b92c0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97157379"
---
# <a name="supporting-idispeventimpl"></a>IDispEventImpl desteği

[IDispEventImpl](../atl/reference/idispeventimpl-class.md) şablon sınıfı, ATL sınıfınıza bağlantı noktası havuzları için destek sağlamak üzere kullanılabilir. Bir bağlantı noktası havuzu, sınıfınızın dış COM nesnelerinden tetiklenen olayları işlemesini sağlar. Bu bağlantı noktası havuzları, sınıfınızın sağlandığı bir olay havuzu eşlemesi ile eşleştirilir.

Sınıfınız için bir bağlantı noktası havuzunu doğru şekilde uygulamak için aşağıdaki adımların tamamlanması gerekir:

- Her dış nesne için tür kitaplıklarını içeri aktar

- Arabirimleri bildirme `IDispEventImpl`

- Olay havuzu eşlemesi bildirme

- Bağlantı noktalarını önerme ve önerme

Bir bağlantı noktası havuzunu uygulamayla ilgili adımlar yalnızca sınıfınızın başlık dosyası (. h) değiştirilerek gerçekleştirilir.

## <a name="importing-the-type-libraries"></a>Tür kitaplıklarını içeri aktarma

Olaylarını işlemek istediğiniz her dış nesne için tür kitaplığını içeri aktarmanız gerekir. Bu adım, işlenebilen olayları tanımlar ve olay havuzu eşlemesini bildirirken kullanılan bilgileri sağlar. [#İmport](../preprocessor/hash-import-directive-cpp.md) yönergesi bunu gerçekleştirmek için kullanılabilir. `#import`Sınıfınızın başlık dosyasına (. h) destekleyeceği her bir dağıtım arabirimi için gerekli yönerge satırlarını ekleyin.

Aşağıdaki örnek, bir dış COM sunucusunun () tür kitaplığını içeri aktarır `MSCAL.Calendar.7` :

[!code-cpp[NVC_ATL_Windowing#141](../atl/codesnippet/cpp/supporting-idispeventimpl_1.h)]

> [!NOTE]
> `#import`Destekleyeceği her bir dış tür kitaplığı için ayrı bir deyiminiz olmalıdır.

## <a name="declaring-the-idispeventimpl-interfaces"></a>IDispEventImpl arabirimlerini bildirme

Her dağıtım arabiriminin tür kitaplıklarını içeri aktardığınıza göre, `IDispEventImpl` her harici dağıtım arabirimi için ayrı arabirimler bildirmeniz gerekir. `IDispEventImpl`Her dış nesne için bir arabirim bildirimi ekleyerek sınıfınızın bildirimini değiştirin. Parametreler hakkında daha fazla bilgi için, bkz. [IDispEventImpl](../atl/reference/idispeventimpl-class.md).

Aşağıdaki kod, `DCalendarEvents` sınıfına göre uygulanan com nesnesi için arabirimi için iki bağlantı noktası havuzları bildirir `CMyCompositCtrl2` :

[!code-cpp[NVC_ATL_Windowing#142](../atl/codesnippet/cpp/supporting-idispeventimpl_2.h)]

## <a name="declaring-an-event-sink-map"></a>Olay havuzu haritasını bildirme

Olay bildirimlerinin uygun işlev tarafından işlenebilmesi için, sınıfınızın her bir olayı doğru işleyiciye yönlendirmelidir. Bu, bir olay havuzu eşlemesi bildirerek elde edilir.

ATL, bu eşlemeyi daha kolay hale getirmek için [BEGIN_SINK_MAP](reference/composite-control-macros.md#begin_sink_map), [END_SINK_MAP](reference/composite-control-macros.md#end_sink_map)ve [SINK_ENTRY_EX](reference/composite-control-macros.md#sink_entry_ex)çeşitli makroları sağlar. Standart biçim aşağıdaki gibidir:

```cpp
BEGIN_SINK_MAP(comClass)
  SINK_ENTRY_EX(id, iid, dispid, func)
  . . . //additional external event entries
END_SINK_MAP()
```

Aşağıdaki örnek, iki olay işleyicileriyle bir olay havuzu eşlemesi bildirir:

[!code-cpp[NVC_ATL_Windowing#136](../atl/codesnippet/cpp/supporting-idispeventimpl_3.h)]

Uygulama neredeyse tamamlanmıştır. Son adım, dış arabirimlerin geri karşılanarak ve açığa sürme ile ilgilidir.

## <a name="advising-and-unadvising-the-idispeventimpl-interfaces"></a>IDispEventImpl arabirimlerini Inceleme ve geri getirme

Son adım, tüm bağlantı noktalarını uygun zamanlarda planlayarak (veya geri alacak) bir yöntemi uygulamaktır. Bu danışmanın, dış istemciler ve nesneniz arasındaki iletişimin gerçekleşmesi için yapılması gerekir. Nesneniz görünür hale gelmeden önce, nesnenizin desteklediği her dış dağıtım arabirimi giden arabirimler için sorgulanır. Bir bağlantı oluşturulur ve nesneden olayları işlemek için giden arabirimine bir başvuru kullanılır. Bu yordam "danışmanlama" olarak adlandırılır.

Nesneniz dış arabirimler ile bittikten sonra, giden arabirimlere artık sınıfınız tarafından kullanıldıklarından bildirimde bulunulmalıdır. Bu işlem "geri alınıyor" olarak anılacaktır.

COM nesnelerinin benzersiz yapısı nedeniyle, bu yordam, uygulamalar arasında ayrıntılı ve yürütme olarak değişir. Bu ayrıntılar, bu konunun kapsamı dışındadır ve değinilmemiş.

## <a name="see-also"></a>Ayrıca bkz.

[ATL COM nesnelerinin temelleri](../atl/fundamentals-of-atl-com-objects.md)
