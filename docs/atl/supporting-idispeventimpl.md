---
title: IDispEventImpl destekleyen | Microsoft Docs
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
ms.openlocfilehash: 680396ae912cca5f19e87697e7de0033213cc963
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="supporting-idispeventimpl"></a>IDispEventImpl destekleme
Şablon sınıfı [IDispEventImpl](../atl/reference/idispeventimpl-class.md) bağlantı noktası havuzlarını ATL sınıfınızda desteği sağlamak için kullanılabilir. Bir bağlantı noktası havuzu dış COM nesneleri tetiklenen olayları işlemek, sınıf sağlar. Bu bağlantı noktası havuzlarını sınıfı tarafından sağlanan bir olay havuz eşlemesi ile eşlenir.  
  
 Sınıfınız için bir bağlantı noktası havuzu düzgün bir şekilde uygulamak için aşağıdaki adımlar tamamlanmalıdır:  
  
-   Dış her nesne türü kitaplıkları içeri aktarma  
  
-   Bildirme `IDispEventImpl` arabirimleri  
  
-   Bir olay havuz eşlemesi bildirme  
  
-   Öneri ve bağlantı noktaları unadvise  
  
 Bir bağlantı noktası havuzu uygulama adımlarını tüm yalnızca üstbilgi dosyası (.h) sınıfınızın değiştirerek gerçekleştirilebilir.  
  
## <a name="importing-the-type-libraries"></a>Tür kitaplıkları içeri aktarma  
 Olayları ele almak istediğiniz her dış nesne için tür kitaplığı içeri aktarmanız gerekir. Bu adım işlenebilir olayları tanımlar ve olay havuz eşlemesi bildirirken kullanılan bilgi sağlar. [#İmport](../preprocessor/hash-import-directive-cpp.md) yönergesi, bunu gerçekleştirmek için kullanılabilir. Gerekli eklemek `#import` yönerge satırları sınıfınız için üstbilgi dosyası (.h) destekleneceğini her gönderme arabirimi için.  
  
 Aşağıdaki örnek bir dış COM sunucusu tür kitaplığı içeri aktarır (`MSCAL.Calendar.7`):  
  
 [!code-cpp[NVC_ATL_Windowing#141](../atl/codesnippet/cpp/supporting-idispeventimpl_1.h)]  
  
> [!NOTE]
>  Ayrı bir olmalıdır `#import` desteklediğiniz her dış tür kitaplığı bildirimi.  
  
## <a name="declaring-the-idispeventimpl-interfaces"></a>IDispEventImpl arabirimleri bildirme  
 Her gönderme arabirimi tür kitaplıklarının içeri aktardığınız, ayrı bildirmek gereken `IDispEventImpl` arabirimleri her dış gönderme arabirimi. Sınıfınızda bildirimi ekleyerek değiştirmeye bir `IDispEventImpl` bildirimi dış her nesne için arabirim. Parametreler hakkında daha fazla bilgi için bkz: [IDispEventImpl](../atl/reference/idispeventimpl-class.md).  
  
 Aşağıdaki kod, için iki bağlantı noktası havuzlarını bildirir `DCalendarEvents` sınıfı tarafından uygulanan COM nesnesi için arabirimi `CMyCompositCtrl2`:  
  
 [!code-cpp[NVC_ATL_Windowing#142](../atl/codesnippet/cpp/supporting-idispeventimpl_2.h)]  
  
## <a name="declaring-an-event-sink-map"></a>Bir olay havuz eşlemesi bildirme  
 Doğru işlevi tarafından işlenecek olay bildirimleri, sınıfınızın doğru işleyicisine her olay rota gerekir. Bu, bir olay havuz eşlemesi bildirerek sağlanır.  
  
 ATL sağlayan birkaç makroları [BEGIN_SINK_MAP](reference/composite-control-macros.md#begin_sink_map), [END_SINK_MAP](reference/composite-control-macros.md#end_sink_map), ve [SINK_ENTRY_EX](reference/composite-control-macros.md#sink_entry_ex), olduğundan olun; bu eşlemenin daha kolay. Standart biçim aşağıdaki gibidir:  
  
 `BEGIN_SINK_MAP(comClass)`  
  
 `SINK_ENTRY_EX(id, iid, dispid, func)`  
  
 `. . . //additional external event entries`  
  
 `END_SINK_MAP()`  
  
 Aşağıdaki örnek, bir olay havuz eşlemesi iki olay işleyicileri ile bildirir:  
  
 [!code-cpp[NVC_ATL_Windowing#136](../atl/codesnippet/cpp/supporting-idispeventimpl_3.h)]  
  
 Neredeyse tam uygulamasıdır. Son adım advising ve dış arabirimlerin unadvising ilgilidir.  
  
## <a name="advising-and-unadvising-the-idispeventimpl-interfaces"></a>Bildiren ve IDispEventImpl arabirimleri Unadvising  
 Son adım, uygun zamanlarda öneri (unadvise tüm bağlantı noktaları veya kuracağınız) bir yöntem uygulamaktır. Dış istemcilere nesnenizin arasındaki iletişimi gerçekleşebilmesi için öncelikle bu bildiren yapılmalıdır. Nesnenizin görünür duruma gelmesi nesnesi tarafından desteklenen her dış dağıtma arabirimi giden arabirimler için sorgulanır. Bir bağlantı oluşturulur ve giden arabirimi başvuru nesneden olayları işlemek için kullanılır. Bu yordamı "bildiren olarak." olarak adlandırılır  
  
 Nesneniz ile dış arabirimler tamamlandıktan sonra giden arabirimleri bunlar artık sınıfı tarafından kullanılan bildirilmesi gerekir. Bu işlem "unadvising olarak." olarak adlandırılır  
  
 COM nesneleri benzersiz yapısı nedeniyle, bu yordamı, ayrıntı ve uygulamaları arasındaki yürütme değişir. Bu konunun kapsamı dışındadır ve ele alınmayan bu ayrıntıları.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ATL COM Nesnelerinin Temelleri](../atl/fundamentals-of-atl-com-objects.md)

