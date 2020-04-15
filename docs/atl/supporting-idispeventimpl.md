---
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
ms.openlocfilehash: 31beff30a067416f71029c18051f214c8d4429de
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329318"
---
# <a name="supporting-idispeventimpl"></a>IDispEventImpl desteği

Şablon sınıfı [IDispEventImpl,](../atl/reference/idispeventimpl-class.md) ATL sınıfınızdaki bağlantı noktası lavaboları için destek sağlamak için kullanılabilir. Bağlantı noktası lavabosu, sınıfınızın dış COM nesnelerinden ateşlenen olayları işlemesini sağlar. Bu bağlantı noktası lavaboları, sınıfınız tarafından sağlanan bir olay lavabo haritasıyla eşlenir.

Sınıfınız için bir bağlantı noktası lavabosu düzgün uygulamak için aşağıdaki adımların tamamlanması gerekir:

- Her dış nesne için tür kitaplıklarını alma

- Arabirimleri `IDispEventImpl` bildirin

- Olay lavabo haritasını bildirme

- Bağlantı noktalarını tavsiye edin ve bildirmeyin

Bağlantı noktası lavabosunu uygulamayla ilgili adımların tümü, sınıfınızın yalnızca üstbilgi dosyasını (.h) değiştirerek gerçekleştirilir.

## <a name="importing-the-type-libraries"></a>Tür Kitaplıklarını Alma

Olayları işlemek istediğiniz her dış nesne için tür kitaplığını almanız gerekir. Bu adım, işlenebilir olayları tanımlar ve olay lavabo eşlemi bildirirken kullanılan bilgileri sağlar. bunu gerçekleştirmek için [#import](../preprocessor/hash-import-directive-cpp.md) yönergesi kullanılabilir. Destekleyeceğiniz `#import` her gönderiaramı için gerekli yönerge satırlarını sınıfınızın üstbilgi dosyasına (.h) ekleyin.

Aşağıdaki örnek, harici bir COM sunucusunun`MSCAL.Calendar.7`tür kitaplığını içeri aktarma ( ):

[!code-cpp[NVC_ATL_Windowing#141](../atl/codesnippet/cpp/supporting-idispeventimpl_1.h)]

> [!NOTE]
> Destekleyeceğiniz her `#import` dış tür kitaplığı için ayrı bir deyiminolması gerekir.

## <a name="declaring-the-idispeventimpl-interfaces"></a>IDispEventImpl Arayüzlerini Bildirme

Artık her gönderi arabiriminin tür kitaplıklarını içe `IDispEventImpl` aktardığınıza göre, her dış gönderme arabirimi için ayrı arabirimler bildirmeniz gerekir. Her dış nesne için bir `IDispEventImpl` arabirim bildirimi ekleyerek sınıfınızın bildirimini değiştirin. Parametreler hakkında daha fazla bilgi için [bkz.](../atl/reference/idispeventimpl-class.md)

Aşağıdaki kod, sınıf `DCalendarEvents` `CMyCompositCtrl2`tarafından uygulanan COM nesnesi için arabirim için iki bağlantı noktası batması bildirir:

[!code-cpp[NVC_ATL_Windowing#142](../atl/codesnippet/cpp/supporting-idispeventimpl_2.h)]

## <a name="declaring-an-event-sink-map"></a>Olay Lavabo HaritasıNı Bildirme

Olay bildirimlerinin uygun işlev tarafından işleyebilmesi için, sınıfınızın her olayı doğru işleyicisine yönlendirmesi gerekir. Bu bir olay lavabo haritası ilan ederek elde edilir.

ATL, bu eşlemi kolaylaştıran çeşitli makrolar, [BEGIN_SINK_MAP,](reference/composite-control-macros.md#begin_sink_map) [END_SINK_MAP](reference/composite-control-macros.md#end_sink_map)ve [SINK_ENTRY_EX](reference/composite-control-macros.md#sink_entry_ex)sağlar. Standart biçimi aşağıdaki gibidir:

```cpp
BEGIN_SINK_MAP(comClass)
  SINK_ENTRY_EX(id, iid, dispid, func)
  . . . //additional external event entries
END_SINK_MAP()
```

Aşağıdaki örnekte, iki olay işleyicisi olan bir olay lavabo haritası bildirir:

[!code-cpp[NVC_ATL_Windowing#136](../atl/codesnippet/cpp/supporting-idispeventimpl_3.h)]

Uygulama neredeyse tamamlandı. Son adım, dış arabirimlerin tavsiye ve eksikliği ile ilgilidir.

## <a name="advising-and-unadvising-the-idispeventimpl-interfaces"></a>IDispEventImpl Arayüzleri Tavsiye ve Tavsiye Dışı

Son adım, tüm bağlantı noktalarını uygun zamanlarda önerecek (veya tavsiye edilmeyen) bir yöntem uygulamaktır. Bu danışmanlık dış istemciler ve nesne arasında iletişim gerçekleşmeden önce yapılmalıdır. Nesneniz görünür hale gelmeden önce, nesneniz tarafından desteklenen her dış gönderme arabirimi giden arabirimler için sorgulanır. Bir bağlantı kurulur ve nesnedeki olayları işlemek için giden arabirime bir başvuru kullanılır. Bu yordam "danışmanlık" olarak adlandırılır.

Nesneniz dış arabirimlerle tamamlandıktan sonra, giden arabirimler artık sınıfınız tarafından kullanılmadığını bildirmelidir. Bu işlem "tavsiye edilmez" olarak adlandırılır.

COM nesnelerinin benzersiz doğası nedeniyle, bu yordam, ayrıntılı olarak ve yürütme, uygulamalar arasında değişir. Bu ayrıntılar bu konunun kapsamı dışındadır ve ele alınmaz.

## <a name="see-also"></a>Ayrıca bkz.

[ATL COM Nesnelerinin Temelleri](../atl/fundamentals-of-atl-com-objects.md)
