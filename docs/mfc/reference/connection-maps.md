---
title: Bağlantı Eşlemeleri
ms.date: 11/04/2016
helpviewer_keywords:
- connection maps
ms.assetid: 1f25a9bc-6d09-4614-99cf-dc38e8ddfa73
ms.openlocfilehash: 947cd09023ef4028a32db8e2e4e8b33f7e04e0dd
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374799"
---
# <a name="connection-maps"></a>Bağlantı Eşlemeleri

OLE denetimleri arabirimleri diğer uygulamalara maruz bırakabilir. Bu arabirimler yalnızca bir kapsayıcıdan bu denetime erişime izin verir. Bir OLE denetimi diğer OLE nesnelerinin dış arabirimlerine erişmek istiyorsa, bir bağlantı noktası oluşturulmalıdır. Bu bağlantı noktası, olay haritaları veya bildirim işlevleri gibi dış gönderme haritalarına denetim giden erişim sağlar.

Microsoft Hazırlık Sınıf Kitaplığı, bağlantı noktalarını destekleyen bir programlama modeli sunar. Bu modelde, OLE denetimi için arabirimleri veya bağlantı noktalarını belirlemek için "bağlantı eşlemleri" kullanılır. Bağlantı eşlemleri her bağlantı noktası için bir makro içerir. Bağlantı haritaları hakkında daha fazla bilgi için [CConnectionPoint](../../mfc/reference/cconnectionpoint-class.md) sınıfına bakın.

Genellikle, denetim yalnızca iki bağlantı noktasını destekler: biri olaylar için, diğeri özellik bildirimleri için. Bunlar `COleControl` taban sınıf tarafından uygulanır ve denetim yazarı tarafından ek bir çalışma gerektirmez. Sınıfınızda uygulamak istediğiniz ek bağlantı noktaları el ile eklenmelidir. Bağlantı eşlemlerini ve noktalarını desteklemek için MFC aşağıdaki makroları sağlar:

### <a name="connection-map-declaration-and-demarcation"></a>Bağlantı Haritası Bildirimi ve Çizimi

|||
|-|-|
|[BEGIN_CONNECTION_PART](#begin_connection_part)|Ek bir bağlantı noktası uygulayan katıştırılmış bir sınıf bildirir (sınıf bildiriminde kullanılması gerekir).|
|[END_CONNECTION_PART](#end_connection_part)|Bağlantı noktası bildirimini sona erdirin (sınıf bildiriminde kullanılmalıdır).|
|[CONNECTION_IID](#connection_iid)|Denetimin bağlantı noktasının arabirim kimliğini belirtir.|
|[DECLARE_CONNECTION_MAP](#declare_connection_map)|Bir bağlantı eşleminin bir sınıfta kullanılacağını bildirir (sınıf bildiriminde kullanılması gerekir).|
|[BEGIN_CONNECTION_MAP](#begin_connection_map)|Bağlantı eşlemi tanımını başla (sınıf uygulamasında kullanılmalıdır).|
|[END_CONNECTION_MAP](#end_connection_map)|Bağlantı eşlemi tanımını sona erdirin (sınıf uygulamasında kullanılmalıdır).|
|[CONNECTION_PART](#connection_part)|Denetimin bağlantı haritasında bir bağlantı noktası belirtir.|

Aşağıdaki işlevler, bağlantı noktalarını kullanarak bir bağlantı nın kurulmasına ve kesilmesine yardımcı olur:

### <a name="initializationtermination-of-connection-points"></a>Bağlantı Noktalarının Başlatılması/Sonlandırılması

|||
|-|-|
|[AfxConnectionAdvise](#afxconnectionadvise)|Kaynak ve lavabo arasında bir bağlantı kurar.|
|[AfxConnectionTavsiye](#afxconnectionunadvise)|Kaynak ve lavabo arasındaki bağlantıyı koparır.|

## <a name="begin_connection_part"></a><a name="begin_connection_part"></a>BEGIN_CONNECTION_PART

Olay ve özellik bildirim bağlantı noktalarının ötesindeki ek bağlantı noktalarının tanımını başlatmak için BEGIN_CONNECTION_PART makroyu kullanın.

```
BEGIN_CONNECTION_PART(theClass, localClass)
```

### <a name="parameters"></a>Parametreler

*theClass*<br/>
Bağlantı noktası bu olan denetim sınıfının adını belirtir.

*localClass*<br/>
Bağlantı noktasını uygulayan yerel sınıfın adını belirtir.

### <a name="remarks"></a>Açıklamalar

Sınıfınızın üye işlevlerini tanımlayan bildirim (.h) dosyasında, BEGIN_CONNECTION_PART makrosuyla bağlantı noktasını başlatın, ardından CONNECTION_IID makroyu ve uygulamak istediğiniz diğer üye işlevleri ekleyin ve END_CONNECTION_PART makrosuyla bağlantı noktası eşlemi tamamlayın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdisp.h

## <a name="end_connection_part"></a><a name="end_connection_part"></a>END_CONNECTION_PART

Bağlantı noktanızın bildirimini sona erdirin.

```
END_CONNECTION_PART(localClass)
```

### <a name="parameters"></a>Parametreler

*localClass*<br/>
Bağlantı noktasını uygulayan yerel sınıfın adını belirtir.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdisp.h

## <a name="connection_iid"></a><a name="connection_iid"></a>CONNECTION_IID

OLE denetiminiz tarafından desteklenen bir bağlantı noktası için arabirim kimliği tanımlamak için BEGIN_CONNECTION_PART ve END_CONNECTION_PART makroları arasında kullanın.

```
CONNECTION_IID(iid)
```

### <a name="parameters"></a>Parametreler

*ııd*<br/>
Bağlantı noktası tarafından çağrılan arabirimin arabirim kimliği.

### <a name="remarks"></a>Açıklamalar

*iid* bağımsız değişkeni, bağlantı noktasının bağlı lavabolarında çağıracağı arabirimi tanımlamak için kullanılan bir arabirim kimliğidir. Örneğin:

[!code-cpp[NVC_MFCConnectionPoints#10](../../mfc/codesnippet/cpp/connection-maps_1.h)]

`ISinkInterface` arabirimi çağıran bir bağlantı noktası belirtir.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdisp.h

## <a name="declare_connection_map"></a><a name="declare_connection_map"></a>DECLARE_CONNECTION_MAP

Programınızdaki türetilmiş her `COleControl`sınıf, denetiminizin desteklediği ek bağlantı noktalarını belirtmek için bir bağlantı eşlemi sağlayabilir.

```
DECLARE_CONNECTION_MAP()
```

### <a name="remarks"></a>Açıklamalar

Denetiminiz ek noktaları destekliyorsa, sınıf bildirgenizin sonundaki DECLARE_CONNECTION_MAP makroyu kullanın. Daha sonra, sınıfın üye işlevlerini tanımlayan .cpp dosyasında, BEGIN_CONNECTION_MAP makroyu, denetimin bağlantı noktalarının her biri için makroCONNECTION_PART ve bağlantı haritasının sonunu bildirmek için makro END_CONNECTION_MAP kullanın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdisp.h

## <a name="begin_connection_map"></a><a name="begin_connection_map"></a>BEGIN_CONNECTION_MAP

Programınızdaki türetilmiş her `COleControl`sınıf, denetiminizin destekleyeceği bağlantı noktalarını belirtmek için bir bağlantı eşlemi sağlayabilir.

```
BEGIN_CONNECTION_MAP(theClass, theBase)
```

### <a name="parameters"></a>Parametreler

*theClass*<br/>
Bağlantı haritası bu olan denetim sınıfının adını belirtir.

*theBase*<br/>
*Sınıfın*taban sınıfının adını belirtir.

### <a name="remarks"></a>Açıklamalar

Uygulamada (. CPP) sınıfınızın üye işlevlerini tanımlayan dosya, BEGIN_CONNECTION_MAP makroile bağlantı eşlemi başlatın, ardından [CONNECTION_PART](#connection_part) makroyu kullanarak bağlantı noktalarınızın her biri için makro girişleri ekleyin. Son olarak, [END_CONNECTION_MAP](#end_connection_map) makrosuyla bağlantı haritasını tamamlayın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdisp.h

## <a name="end_connection_map"></a><a name="end_connection_map"></a>END_CONNECTION_MAP

Bağlantı haritanızın tanımını sona erdirer.

```
END_CONNECTION_MAP()
```

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdisp.h

## <a name="connection_part"></a><a name="connection_part"></a>CONNECTION_PART

OLE denetiminiz için bir bağlantı noktasını belirli bir arabirim kimliğiyle eşler.

```
CONNECTION_PART(theClass, iid, localClass)
```

### <a name="parameters"></a>Parametreler

*theClass*<br/>
Bağlantı noktası bu olan denetim sınıfının adını belirtir.

*ııd*<br/>
Bağlantı noktası tarafından çağrılan arabirimin arabirim kimliği.

*localClass*<br/>
Bağlantı noktasını uygulayan yerel sınıfın adını belirtir.

### <a name="remarks"></a>Açıklamalar

Örneğin:

[!code-cpp[NVC_MFCConnectionPoints#2](../../mfc/codesnippet/cpp/connection-maps_2.cpp)]

arabirimi çağıran bir bağlantı noktası olan bir `IID_ISinkInterface` bağlantı eşlemi uygular.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdisp.h

## <a name="afxconnectionadvise"></a><a name="afxconnectionadvise"></a>AfxConnectionAdvise

*PUnkSrc*tarafından belirtilen bir kaynak arasında bağlantı kurmak için bu işlevi arayın ve *pUnkSink*tarafından belirtilen bir lavabo.

```
BOOL AFXAPI AfxConnectionAdvise(
    LPUNKNOWN pUnkSrc,
    REFIID iid,
    LPUNKNOWN pUnkSink,
    BOOL bRefCount,
    DWORD FAR* pdwCookie);
```

### <a name="parameters"></a>Parametreler

*pUnkSrc*<br/>
Arabirimi çağıran nesneye işaretçi.

*pUnkSink*<br/>
Arabirimi uygulayan nesneye işaretçi.

*ııd*<br/>
Bağlantının arabirim kimliği.

*bRefCount*<br/>
TRUE, bağlantıyı oluşturmanın *pUnkSink'in* başvuru sayısının artışa neden olması gerektiğini gösterir. FALSE, başvuru sayısının artmaması gerektiğini gösterir.

*pdwCookie*<br/>
Bağlantı tanımlayıcısı döndürülen bir DWORD işaretçisi. Bu değer, bağlantı `AfxConnectionUnadvise` kesilirken *dwCookie* parametresi olarak geçirilmelidir.

### <a name="return-value"></a>Dönüş Değeri

Bir bağlantı kurulmuşsa sıfır olmayan; aksi takdirde 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCConnectionPoints#8](../../mfc/codesnippet/cpp/connection-maps_3.cpp)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxctl.h

## <a name="afxconnectionunadvise"></a><a name="afxconnectionunadvise"></a>AfxConnectionTavsiye

*PUnkSrc*tarafından belirtilen bir kaynak arasındaki bağlantıyı kesmek için bu işlevi arayın ve *pUnkSink*tarafından belirtilen bir lavabo.

```
BOOL AFXAPI AfxConnectionUnadvise(
    LPUNKNOWN pUnkSrc,
    REFIID iid,
    LPUNKNOWN pUnkSink,
    BOOL bRefCount,
    DWORD dwCookie);
```

### <a name="parameters"></a>Parametreler

*pUnkSrc*<br/>
Arabirimi çağıran nesneye işaretçi.

*pUnkSink*<br/>
Arabirimi uygulayan nesneye işaretçi.

*ııd*<br/>
Bağlantı noktası arabiriminin arabirim kimliği.

*bRefCount*<br/>
TRUE, bağlantının kesilmesinin *pUnkSink'in* başvuru sayısının kesilmesine neden olması gerektiğini gösterir. FALSE, başvuru sayısının belirtilmemesi gerektiğini gösterir.

*dwCookie*<br/>
Bağlantı tanımlayıcısı tarafından `AfxConnectionAdvise`döndürülür.

### <a name="return-value"></a>Dönüş Değeri

Bağlantı kesildiyse sıfırsız; aksi takdirde 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCConnectionPoints#9](../../mfc/codesnippet/cpp/connection-maps_4.cpp)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxctl.h

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve Küreseller](../../mfc/reference/mfc-macros-and-globals.md)
