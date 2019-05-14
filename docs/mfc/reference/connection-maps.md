---
title: Bağlantı Eşlemeleri
ms.date: 11/04/2016
helpviewer_keywords:
- connection maps
ms.assetid: 1f25a9bc-6d09-4614-99cf-dc38e8ddfa73
ms.openlocfilehash: a36c112de8c760f91afd5cf544b355f7cb8e1bed
ms.sourcegitcommit: 934cb53fa4cb59fea611bfeb9db110d8d6f7d165
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65612279"
---
# <a name="connection-maps"></a>Bağlantı Eşlemeleri

OLE denetimleri diğer uygulamalara arabirimleri kullanıma sunma olanağına sahip olursunuz. Bu arabirimler yalnızca bu denetime kapsayıcı erişime izin verecek. Diğer OLE nesneleri Dış arabirimler erişmek bir OLE denetim isterse, bağlantı noktası kurulması gerekir. Bu bağlantı noktasının giden olay eşlemeleri veya bildirim işlevleri gibi dış gönderme eşlemeleri için erişim denetim sağlar.

Microsoft Foundation Class Kitaplığı, bağlantı noktaları destekleyen bir programlama modeli sunar. Bu modelde, "haritalar" bağlantı arabirimleri veya OLE denetimi için bağlantı noktalarını belirlemek için kullanılır. Bağlantı eşlemeleri, her bir bağlantı noktası için bir makro içerir. Bağlantı eşlemeleri hakkında daha fazla bilgi için bkz. [CConnectionPoint](../../mfc/reference/cconnectionpoint-class.md) sınıfı.

Bir denetimi yalnızca iki bağlantı noktaları genellikle destekleyecek: biri olayları, diğeri için özellik bildirimleri. Bunlar tarafından uygulanan `COleControl` temel sınıfı ve hiçbir ek iş denetim yazıcı tarafından gerektirir. Sınıfınızda uygulamak istediğiniz herhangi bir ek bağlantı noktalarını el ile eklenmesi gerekir. Bağlantı eşlemeleri ve noktalarının desteklenmesi için aşağıdaki makroları MFC sağlar:

### <a name="connection-map-declaration-and-demarcation"></a>Bağlantı eşlemesi bildirim ve düzenleme

|||
|-|-|
|[BEGIN_CONNECTION_PART](#begin_connection_part)|Bir ek bağlantı noktası (sınıf bildirimi içinde kullanılmalıdır) uygulayan katıştırılmış bir sınıfı bildirir.|
|[END_CONNECTION_PART](#end_connection_part)|Bildirimi bir bağlantı noktası (sınıf bildirimi içinde kullanılmalıdır) sona erer.|
|[CONNECTION_IID](#connection_iid)|Denetim bağlantı noktası arabirimi Kimliğini belirtir.|
|[DECLARE_CONNECTION_MAP](#declare_connection_map)|Bir bağlantı eşlemesi (sınıf bildirimi içinde kullanılmalıdır) bir sınıf içinde kullanılacak bildirir.|
|[BEGIN_CONNECTION_MAP](#begin_connection_map)|(Sınıfı uygulamasında kullanılmalıdır) bir bağlantı eşlemesi tanımını başlar.|
|[END_CONNECTION_MAP](#end_connection_map)|(Sınıfı uygulamasında kullanılmalıdır) bir bağlantı eşlemesi tanımını sonlandırır.|
|[CONNECTION_PART](#connection_part)|Bir bağlantı noktası denetim bağlantı eşlemesinde belirtir.|

Aşağıdaki işlevleri bir havuz oluşturma ve bağlantı noktalarını kullanarak bir bağlantıyı kesmeden yardımcı olur:

### <a name="initializationtermination-of-connection-points"></a>Başlatma/sonlandırılması, bağlantı noktaları

|||
|-|-|
|[AfxConnectionAdvise](#afxconnectionadvise)|Bir kaynak ve havuz arasında bir bağlantı kurar.|
|[AfxConnectionUnadvise](#afxconnectionunadvise)|Bir kaynak ve havuz arasında bağlantıyı keser.|

##  <a name="begin_connection_part"></a>  BEGIN_CONNECTION_PART

Begın_connectıon_part makrosu, olay ve özellik bildirim bağlantı noktalarını ötesinde ek bağlantı noktalarını tanımını başlamak için kullanın.

```
BEGIN_CONNECTION_PART(theClass, localClass)
```

### <a name="parameters"></a>Parametreler

*Sınıfın*<br/>
Bağlantı noktası bu denetimi sınıfın adını belirtir.

*localClass*<br/>
Bağlantı noktası uygulayan yerel sınıfın adını belirtir.

### <a name="remarks"></a>Açıklamalar

Sınıfınız için üye işlevleri tanımlayan bildirimi (.h) dosyası, begın_connectıon_part makrosu ile başlangıç bağlantı noktası sonra connectıon_ııd makrosu ve uygulamak istediğiniz diğer üye işlevlerini ekleyin ve bağlantıyı tamamlamak end_connectıon_part makrosu ile harita noktası.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdisp.h

##  <a name="end_connection_part"></a>  END_CONNECTION_PART

Bağlantı noktanız bildirimi sona erer.

```
END_CONNECTION_PART(localClass)
```

### <a name="parameters"></a>Parametreler

*localClass*<br/>
Bağlantı noktası uygulayan yerel sınıfın adını belirtir.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdisp.h

##  <a name="connection_iid"></a>  CONNECTION_IID

Begın_connectıon_part end_connectıon_part arasında makroları, OLE denetimi tarafından desteklenen bir bağlantı noktası için bir arabirim kimliği tanımlamak için kullanın.

```
CONNECTION_IID(iid)
```

### <a name="parameters"></a>Parametreler

*IID*<br/>
Bağlantı noktası tarafından adlandırılan arabirimi arabirim kimliği.

### <a name="remarks"></a>Açıklamalar

*IID* bağımsız değişkeni olan bağlantı noktası üzerinde bağlı kendi havuzlarını çağıran arabirim tanımlamak için kullanılan arabirim. Örneğin:

[!code-cpp[NVC_MFCConnectionPoints#10](../../mfc/codesnippet/cpp/connection-maps_1.h)]

çağıran bir bağlantı noktasını belirtir `ISinkInterface` arabirimi.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdisp.h

##  <a name="declare_connection_map"></a>  DECLARE_CONNECTION_MAP

Her `COleControl`-programınızı türetilen sınıfta denetiminiz destekleyen ek bağlantı noktaları belirtmek için bir bağlantı eşlemesi sağlayabilir.

```
DECLARE_CONNECTION_MAP()
```

### <a name="remarks"></a>Açıklamalar

Denetim noktaları ek destekliyorsa, sınıf bildiriminin sonuna declare_connectıon_map makrosu kullanın. Ardından, sınıfın üye işlevleri tanımlar .cpp dosyası begın_connectıon_map makrosu, connectıon_part makrosu her denetimin bağlantı noktaları ve end_connectıon_map makrosu bağlantı eşlemesi sonuna bildirmek için kullanın.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdisp.h

##  <a name="begin_connection_map"></a>  BEGIN_CONNECTION_MAP

Her `COleControl`-programınızı türetilen sınıfta denetiminizin destekleyeceği bağlantı noktaları belirtmek için bir bağlantı eşlemesi sağlayabilir.

```
BEGIN_CONNECTION_MAP(theClass, theBase)
```

### <a name="parameters"></a>Parametreler

*Sınıfın*<br/>
Bu eşleme olan bağlantı denetimi sınıfın adını belirtir.

*theBase*<br/>
Taban sınıfının adını belirtir *sınıfın*.

### <a name="remarks"></a>Açıklamalar

Uygulamasında (. Üyeyi tanımlayan CPP) dosya sınıfınız için işlevleri, bağlantı eşlemesi begın_connectıon_map makrosu ile başlayın, ardından her kullanarak, bağlantı noktaları için makro girişler ekleyin [connectıon_part](#connection_part) makrosu. Son olarak, bağlantı haritayla tamamlamak [end_connectıon_map](#end_connection_map) makrosu.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdisp.h

##  <a name="end_connection_map"></a>  END_CONNECTION_MAP

Bağlantı haritanızı tanımını sonlandırır.

```
END_CONNECTION_MAP()
```

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdisp.h

##  <a name="connection_part"></a>  CONNECTION_PART

OLE denetim için bir bağlantı noktası bir arabirimin kimliğine eşleyen

```
CONNECTION_PART(theClass, iid, localClass)
```

### <a name="parameters"></a>Parametreler

*Sınıfın*<br/>
Bağlantı noktası bu denetimi sınıfın adını belirtir.

*IID*<br/>
Bağlantı noktası tarafından adlandırılan arabirimi arabirim kimliği.

*localClass*<br/>
Bağlantı noktası uygulayan yerel sınıfın adını belirtir.

### <a name="remarks"></a>Açıklamalar

Örneğin:

[!code-cpp[NVC_MFCConnectionPoints#2](../../mfc/codesnippet/cpp/connection-maps_2.cpp)]

çağıran bir bağlantı noktası ile bir bağlantı eşleme uygular `IID_ISinkInterface` arabirimi.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdisp.h

##  <a name="afxconnectionadvise"></a>  AfxConnectionAdvise

Tarafından belirtilen bir kaynağı arasında bağlantı kurmak için bu işlevi çağırın *pUnkSrc*ve bir havuz tarafından belirtilen, *pUnkSink*.

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
Arabirimi çağıran nesneye bir işaretçi.

*pUnkSink*<br/>
Arabirimini uygulayan nesnenin bir işaretçi.

*IID*<br/>
Bağlantı arabirim kimliği.

*bRefCount*<br/>
TRUE gösterir bağlantıyı başvuru sayısını edilmesini *pUnkSink* artırılacak. Başvuru sayısı değil arttırılarak FALSE gösterir.

*pdwCookie*<br/>
Bağlantı tanımlayıcı burada döndürülür DWORD işaretçisi. Bu değer olarak geçirilmelidir *dwCookie* parametresi `AfxConnectionUnadvise` bağlantısı kesilirken.

### <a name="return-value"></a>Dönüş Değeri

Bir bağlantı kuruldu olursa sıfır dışı; Aksi durumda 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCConnectionPoints#8](../../mfc/codesnippet/cpp/connection-maps_3.cpp)]

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxctl.h

##  <a name="afxconnectionunadvise"></a>  AfxConnectionUnadvise

Tarafından belirtilen bir kaynağı arasındaki bağlantıyı kesmek için bu işlevi çağırın *pUnkSrc*ve bir havuz tarafından belirtilen, *pUnkSink*.

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
Arabirimi çağıran nesneye bir işaretçi.

*pUnkSink*<br/>
Arabirimini uygulayan nesnenin bir işaretçi.

*IID*<br/>
Bağlantı noktası arabirimi arabirim kimliği.

*bRefCount*<br/>
TRUE, bağlantı kesme başvuru sayısını edilmesini gösterir *pUnkSink* azaltılacak. Başvuru sayısı indirildiği olmamalıdır FALSE gösterir.

*dwCookie*<br/>
Tarafından döndürülen bağlantı tanımlayıcısı `AfxConnectionAdvise`.

### <a name="return-value"></a>Dönüş Değeri

Bir bağlantı kesildi olursa sıfır dışı; Aksi durumda 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCConnectionPoints#9](../../mfc/codesnippet/cpp/connection-maps_4.cpp)]

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxctl.h

## <a name="see-also"></a>Ayrıca bkz.

[Makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md)
