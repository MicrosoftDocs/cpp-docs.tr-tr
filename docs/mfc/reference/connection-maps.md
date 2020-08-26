---
title: Bağlantı Eşlemeleri
ms.date: 11/04/2016
helpviewer_keywords:
- connection maps
ms.assetid: 1f25a9bc-6d09-4614-99cf-dc38e8ddfa73
ms.openlocfilehash: 517017e9e60b86e96daa24f7822538e91c609fb4
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88841421"
---
# <a name="connection-maps"></a>Bağlantı Eşlemeleri

OLE denetimleri, arabirimleri diğer uygulamalar için kullanıma sunabilebiliyor. Bu arabirimler yalnızca bir kapsayıcıdan bu denetime erişim izni verir. OLE denetimi diğer OLE nesnelerinin dış arabirimlerine erişmek istiyorsa bir bağlantı noktası oluşturulmalıdır. Bu bağlantı noktası, olay haritaları veya bildirim işlevleri gibi dış dağıtım haritalarına giden erişim denetimi sağlar.

Microsoft Foundation Class Kitaplığı bağlantı noktalarını destekleyen bir programlama modeli sunar. Bu modelde, OLE denetimine yönelik arabirimleri veya bağlantı noktalarını belirlemek için "bağlantı haritaları" kullanılır. Bağlantı haritaları her bağlantı noktası için bir makro içerir. Bağlantı eşlemeleri hakkında daha fazla bilgi için bkz. [CConnectionPoint](../../mfc/reference/cconnectionpoint-class.md) sınıfı.

Genellikle, bir denetim yalnızca iki bağlantı noktasını destekler: bir olay ve biri özellik bildirimleri için. Bunlar temel sınıf tarafından uygulanır `COleControl` ve denetim yazıcısı tarafından ek iş gerektirmez. Sınıfınıza uygulamak istediğiniz ek bağlantı noktalarının el ile eklenmesi gerekir. MFC bağlantı eşlemelerini ve noktalarını desteklemek için aşağıdaki makroları sağlar:

### <a name="connection-map-declaration-and-demarcation"></a>Bağlantı eşleme bildirimi ve demarcation

|Ad|Açıklama|
|-|-|
|[BEGIN_CONNECTION_PART](#begin_connection_part)|Ek bağlantı noktası uygulayan gömülü bir sınıf bildirir (sınıf bildiriminde kullanılması gerekir).|
|[END_CONNECTION_PART](#end_connection_part)|Bir bağlantı noktasının bildirimini sonlandırır (sınıf bildiriminde kullanılması gerekir).|
|[CONNECTION_IID](#connection_iid)|Denetimin bağlantı noktasının arabirim KIMLIĞINI belirtir.|
|[DECLARE_CONNECTION_MAP](#declare_connection_map)|Bir bağlantı eşlemesinin bir sınıfta kullanılacağını bildirir (sınıf bildiriminde kullanılması gerekir).|
|[BEGIN_CONNECTION_MAP](#begin_connection_map)|Bir bağlantı eşlemesinin tanımını başlatır (sınıf uygulamasında kullanılması gerekir).|
|[END_CONNECTION_MAP](#end_connection_map)|Bir bağlantı eşlemesinin tanımını sonlandırır (sınıf uygulamasında kullanılması gerekir).|
|[CONNECTION_PART](#connection_part)|Denetimin bağlantı eşlemesindeki bir bağlantı noktasını belirtir.|

Aşağıdaki işlevler bağlantı noktalarını kullanarak bağlantı oluşturma ve bağlantının kesilmesi konusunda bir havuza yardımcı olur:

### <a name="initializationtermination-of-connection-points"></a>Bağlantı noktalarının başlatılması/sonlandırılması

|Ad|Açıklama|
|-|-|
|[AfxConnectionAdvise](#afxconnectionadvise)|Kaynak ve havuz arasında bir bağlantı kurar.|
|[AfxConnectionUnadvise](#afxconnectionunadvise)|Kaynak ve havuz arasındaki bağlantıyı keser.|

## <a name="begin_connection_part"></a><a name="begin_connection_part"></a> BEGIN_CONNECTION_PART

Olay ve Özellik bildirim bağlantı noktalarının ötesinde ek bağlantı noktalarının tanımına başlamak için BEGIN_CONNECTION_PART makrosunu kullanın.

```
BEGIN_CONNECTION_PART(theClass, localClass)
```

### <a name="parameters"></a>Parametreler

*Sınıf*<br/>
Bağlantı noktası bu olan denetim sınıfının adını belirtir.

*localClass*<br/>
Bağlantı noktasını uygulayan yerel sınıfın adını belirtir.

### <a name="remarks"></a>Açıklamalar

Sınıfınız için üye işlevlerini tanımlayan bildirim (. h) dosyasında, bağlantı noktasını BEGIN_CONNECTION_PART makroyla başlatın, sonra CONNECTION_IID makrosunu ve uygulamak istediğiniz diğer tüm üye işlevleri ekleyin ve bağlantı noktası haritasını END_CONNECTION_PART makroyla doldurun.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** AfxDisp. h

## <a name="end_connection_part"></a><a name="end_connection_part"></a> END_CONNECTION_PART

Bağlantı noktanlarınızın bildirimini sonlandırır.

```
END_CONNECTION_PART(localClass)
```

### <a name="parameters"></a>Parametreler

*localClass*<br/>
Bağlantı noktasını uygulayan yerel sınıfın adını belirtir.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** AfxDisp. h

## <a name="connection_iid"></a><a name="connection_iid"></a> CONNECTION_IID

OLE denetiminiz tarafından desteklenen bir bağlantı noktası için arabirim KIMLIĞI tanımlamak üzere BEGIN_CONNECTION_PART ve END_CONNECTION_PART makroları arasında kullanın.

```
CONNECTION_IID(iid)
```

### <a name="parameters"></a>Parametreler

*'si*<br/>
Bağlantı noktası tarafından çağrılan arabirimin arabirim KIMLIĞI.

### <a name="remarks"></a>Açıklamalar

*IID* bağımsız değişkeni, bağlantı noktasının bağlı olan havuzları üzerinde çağıracaksınız arabirimi tanımlamak için kullanılan BIR arabirim kimliğidir. Örnek:

[!code-cpp[NVC_MFCConnectionPoints#10](../../mfc/codesnippet/cpp/connection-maps_1.h)]

arabirimi çağıran bir bağlantı noktasını belirtir `ISinkInterface` .

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** AfxDisp. h

## <a name="declare_connection_map"></a><a name="declare_connection_map"></a> DECLARE_CONNECTION_MAP

`COleControl`Programınızdaki her türetilmiş sınıf, denetiminizin desteklediği ek bağlantı noktalarını belirtmek için bir bağlantı eşlemesi sağlayabilir.

```
DECLARE_CONNECTION_MAP()
```

### <a name="remarks"></a>Açıklamalar

Denetiminiz ek noktaları destekliyorsa, sınıf bildirimin sonundaki DECLARE_CONNECTION_MAP makrosunu kullanın. Ardından, sınıfının üye işlevlerini tanımlayan. cpp dosyasında, denetimin bağlantı noktalarının her biri için BEGIN_CONNECTION_MAP makrosunu, CONNECTION_PART makrolarını ve bağlantı eşlemesinin sonunu bildirmek için END_CONNECTION_MAP makrosunu kullanın.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** AfxDisp. h

## <a name="begin_connection_map"></a><a name="begin_connection_map"></a> BEGIN_CONNECTION_MAP

`COleControl`Programınızdaki her türetilmiş sınıf, denetiminizin destekleyeceği bağlantı noktalarını belirtmek için bir bağlantı haritası sağlayabilir.

```
BEGIN_CONNECTION_MAP(theClass, theBase)
```

### <a name="parameters"></a>Parametreler

*Sınıf*<br/>
Bağlantı eşlemesi bu olan denetim sınıfının adını belirtir.

*theBase*<br/>
Sınıfın temel sınıfının adını *belirtir.*

### <a name="remarks"></a>Açıklamalar

Uygulamada (. CPP) sınıfınız için üye işlevleri tanımlayan dosya, bağlantı haritasını BEGIN_CONNECTION_MAP makrosu ile başlatın ve [CONNECTION_PART](#connection_part) makrosunu kullanarak bağlantı noktalarınızın her biri için makro girişleri ekleyin. Son olarak, bağlantı haritasını [END_CONNECTION_MAP](#end_connection_map) makrosu ile doldurun.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** AfxDisp. h

## <a name="end_connection_map"></a><a name="end_connection_map"></a> END_CONNECTION_MAP

Bağlantı haritaınızın tanımını sonlandırır.

```
END_CONNECTION_MAP()
```

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** AfxDisp. h

## <a name="connection_part"></a><a name="connection_part"></a> CONNECTION_PART

OLE denetiminiz için bir bağlantı noktasını belirli bir arabirim KIMLIĞIYLE eşler.

```
CONNECTION_PART(theClass, iid, localClass)
```

### <a name="parameters"></a>Parametreler

*Sınıf*<br/>
Bağlantı noktası bu olan denetim sınıfının adını belirtir.

*'si*<br/>
Bağlantı noktası tarafından çağrılan arabirimin arabirim KIMLIĞI.

*localClass*<br/>
Bağlantı noktasını uygulayan yerel sınıfın adını belirtir.

### <a name="remarks"></a>Açıklamalar

Örnek:

[!code-cpp[NVC_MFCConnectionPoints#2](../../mfc/codesnippet/cpp/connection-maps_2.cpp)]

arabirimi çağıran bir bağlantı noktası ile bağlantı haritası uygular `IID_ISinkInterface` .

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** AfxDisp. h

## <a name="afxconnectionadvise"></a><a name="afxconnectionadvise"></a> AfxConnectionAdvise

*Punksrc*tarafından belirtilen bir kaynak ve *pUnkSink*tarafından belirtilen bir havuz arasında bağlantı kurmak için bu işlevi çağırın.

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
Arabirimi çağıran nesneye yönelik bir işaretçi.

*pUnkSink*<br/>
Arabirimini uygulayan nesneye yönelik bir işaretçi.

*'si*<br/>
Bağlantının arabirim KIMLIĞI.

*bRefCount*<br/>
DOĞRU, bağlantı oluşturmanın *pUnkSink* başvuru sayısının artmasına neden olması gerektiğini gösterir. FALSE, başvuru sayısının arttırılmayacağını gösterir.

*pdwCookie*<br/>
Bir bağlantı tanımlayıcısının döndürüldüğü DWORD için bir işaretçi. Bağlantının bağlantısı kesilirken bu değerin *dwCookie* parametresi olarak geçirilmesi gerekir `AfxConnectionUnadvise` .

### <a name="return-value"></a>Dönüş Değeri

Bağlantı kurulduysa sıfır dışı; Aksi takdirde 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCConnectionPoints#8](../../mfc/codesnippet/cpp/connection-maps_3.cpp)]

### <a name="requirements"></a>Gereksinimler

**Üst bilgi:** afxctl. h

## <a name="afxconnectionunadvise"></a><a name="afxconnectionunadvise"></a> AfxConnectionUnadvise

*Punksrc*tarafından belirtilen bir kaynak ve *pUnkSink*tarafından belirtilen bir havuz arasındaki bağlantının bağlantısını kesmek için bu işlevi çağırın.

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
Arabirimi çağıran nesneye yönelik bir işaretçi.

*pUnkSink*<br/>
Arabirimini uygulayan nesneye yönelik bir işaretçi.

*'si*<br/>
Bağlantı noktası arabiriminin arabirim KIMLIĞI.

*bRefCount*<br/>
DOĞRU, bağlantı bağlantısının kesilmesi, *pUnkSink* başvuru sayısının azaltımına neden olması gerektiğini gösterir. FALSE, başvuru sayısının küçültülemeyeceği anlamına gelir.

*dwCookie*<br/>
Tarafından döndürülen bağlantı tanımlayıcısı `AfxConnectionAdvise` .

### <a name="return-value"></a>Dönüş Değeri

Bağlantının bağlantısı kesildiyse sıfır dışı; Aksi takdirde 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCConnectionPoints#9](../../mfc/codesnippet/cpp/connection-maps_4.cpp)]

### <a name="requirements"></a>Gereksinimler

**Üst bilgi:** afxctl. h

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve genel öğeler](../../mfc/reference/mfc-macros-and-globals.md)
