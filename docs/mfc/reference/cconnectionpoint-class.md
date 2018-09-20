---
title: CConnectionPoint sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CConnectionPoint
- AFXDISP/CConnectionPoint
- AFXDISP/CConnectionPoint::CConnectionPoint
- AFXDISP/CConnectionPoint::GetConnections
- AFXDISP/CConnectionPoint::GetContainer
- AFXDISP/CConnectionPoint::GetIID
- AFXDISP/CConnectionPoint::GetMaxConnections
- AFXDISP/CConnectionPoint::GetNextConnection
- AFXDISP/CConnectionPoint::GetStartPosition
- AFXDISP/CConnectionPoint::OnAdvise
- AFXDISP/CConnectionPoint::QuerySinkInterface
dev_langs:
- C++
helpviewer_keywords:
- CConnectionPoint [MFC], CConnectionPoint
- CConnectionPoint [MFC], GetConnections
- CConnectionPoint [MFC], GetContainer
- CConnectionPoint [MFC], GetIID
- CConnectionPoint [MFC], GetMaxConnections
- CConnectionPoint [MFC], GetNextConnection
- CConnectionPoint [MFC], GetStartPosition
- CConnectionPoint [MFC], OnAdvise
- CConnectionPoint [MFC], QuerySinkInterface
ms.assetid: f0f23a1e-5e8c-41a9-aa6c-1a4793b28e8f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1a762ddfa7a724b392910e681a5ec569dc8b2652
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46407941"
---
# <a name="cconnectionpoint-class"></a>CConnectionPoint sınıfı

Özel bir "bağlantı noktası." adlı diğer OLE nesneleri ile iletişim kurmak için kullanılan arabirim türünü tanımlar

## <a name="syntax"></a>Sözdizimi

```
class CConnectionPoint : public CCmdTarget
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CConnectionPoint::CConnectionPoint](#cconnectionpoint)|Oluşturur bir `CConnectionPoint` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CConnectionPoint::GetConnections](#getconnections)|Tüm bağlantı noktalarının bağlantı eşlemesi alır.|
|[CConnectionPoint::GetContainer](#getcontainer)|Bağlantı eşlemine sahip denetimin kapsayıcısının alır.|
|[CConnectionPoint::GetIID](#getiid)|Bir bağlantı noktasının arabirim kimliği alır.|
|[CConnectionPoint::GetMaxConnections](#getmaxconnections)|Bağlantı noktaları bir denetim tarafından desteklenen maksimum sayısını alır.|
|[CConnectionPoint::GetNextConnection](#getnextconnection)|Bağlantı öğe için bir işaretçi alır *pos*.|
|[CConnectionPoint::GetStartPosition](#getstartposition)|Harita yineleme, geçirilebilir bir konum değeri döndürerek başlar bir `GetNextConnection` çağırın.|
|[CConnectionPoint::OnAdvise](#onadvise)|Oluşturma veya bağlantılarını kesme framework tarafından çağırılır.|
|[CConnectionPoint::QuerySinkInterface](#querysinkinterface)|İstenen havuz arabirim işaretçisi alır.|

## <a name="remarks"></a>Açıklamalar

Uygulama ve bir OLE denetim işlevselliğini göstermek için kullanılan normal OLE arabirimleri, bir bağlantı noktası olayları tetikleme gibi diğer nesneler üzerinde eylem başlatmak ve değişiklik bildirimleri giden bir arabirim uygular.

Bir bağlantı iki bölümden oluşur: "kaynak" ve arabirimi uygulayan nesnenin adlı arabirim, çağıran nesneyle adında "havuz." Bir bağlantı noktası göstererek kaynak havuzlarını kendine bağlantılar kurmak sağlar. Bağlantı noktası mekanizma aracılığıyla kaynak nesnesi havuz'ın uygulama üye işlevleri bir dizi için bir işaretçi alır. Örneğin, havuz tarafından uygulanan bir olay harekete geçirmek için kaynak havuzu'nın uygulama uygun yöntemini çağırabilirsiniz.

Varsayılan olarak, bir `COleControl`-türetilmiş sınıf uygulayan iki bağlantı noktası: olaylar için bir tane ve bir özellik için değişiklik bildirimleri. Bu bağlantılar kullanılır, sırasıyla, olay tetikleyicisinin tetikleme ve ne zaman bir havuz (örneğin, denetimin kapsayıcısı) bildirme için bir özellik değeri değiştirildi. Destek ek bağlantı noktalarını uygulamak OLE denetimleri için de sağlanır. Denetim sınıfınıza uygulanan her ek bağlantı noktası için "bağlantı noktası uygulayan bir bağlantı bölümü" bildirmeniz gerekir. Bir veya daha fazla bağlantı noktası uygularsanız, ayrıca tek bir "bağlantı haritada" Denetim sınıfınıza bildirmeniz gerekir.

Aşağıdaki örnek, bir basit bağlantı Haritası ve için bir bağlantı noktası gösterir `Sample` OLE denetim, iki kod parçalarını oluşan: ilk bölümü noktası ve bağlantı eşlemesi bildirir; bu harita ve noktası ikinci uygular. İlk parça altında denetimi sınıfının bildirimi içine eklenen **korumalı** bölümü:

[!code-cpp[NVC_MFCConnectionPoints#7](../../mfc/codesnippet/cpp/cconnectionpoint-class_1.h)]

Begın_connectıon_part ve end_connectıon_part makroları katıştırılmış bir sınıf bildirme `XSampleConnPt` (türetilen `CConnectionPoint`), bu belirli bağlantı noktası uygular. Herhangi bir geçersiz kılmak istiyorsanız `CConnectionPoint` üye işlevleri, veya üye işlevleri kendi ekleme, bunları bu iki makrolar arasında bildirin. Örneğin, connectıon_ııd makrosu geçersiz kılmaları `CConnectionPoint::GetIID` iki Bu makrolar arasında yerleştirildiğinde üye işlevi.

İkinci kod parçası uygulama dosyasına eklenir (. CPP) denetim sınıfınızın. Bu kod ek bağlantı noktası içeren bağlantı eşlemesi uygulayan `SampleConnPt`:

[!code-cpp[NVC_MFCConnectionPoints#2](../../mfc/codesnippet/cpp/cconnectionpoint-class_2.cpp)]

Bu kod parçalarını ekledikten sonra örnek OLE denetimi için bir bağlantı noktası sunan `ISampleSink` arabirimi.

Genellikle, bağlantı noktaları için birden çok havuzlarını aynı arabirime bağlı yayın olanağı "noktaya" destekler. Aşağıdaki kod parçası, çok noktaya yayın bağlantı noktasındaki her bir havuz ile Yinelem yaparak gerçekleştirilmesi gösterilmektedir:

[!code-cpp[NVC_MFCConnectionPoints#4](../../mfc/codesnippet/cpp/cconnectionpoint-class_3.cpp)]

Bu örnek, üzerinde bağlantıları geçerli kümesini alır. `SampleConnPt` çağrısı ile bağlantı noktası `CConnectionPoint::GetConnections`. Ardından bağlantılar ve çağrılar aracılığıyla yinelenir `ISampleSink::SinkFunc` her etkin bağlantı.

Kullanma hakkında daha fazla bilgi için `CConnectionPoint`, makaleye göz atın [bağlantı noktaları](../../mfc/connection-points.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`CConnectionPoint`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxdisp.h

##  <a name="cconnectionpoint"></a>  CConnectionPoint::CConnectionPoint

Oluşturur bir `CConnectionPoint` nesne.

```
CConnectionPoint();
```

##  <a name="getconnections"></a>  CConnectionPoint::GetConnections

Tüm etkin bağlantılar için bağlantı noktası almak için bu işlevi çağırın.

```
const CPtrArray* GetConnections();
```

### <a name="return-value"></a>Dönüş Değeri

Etkin bağlantılar (iç havuzlar) dizisi için bir işaretçi. Bazı işaretçiler dizisi NULL olabilir. Her bir NULL olmayan işaretçiyi dizideki güvenli bir şekilde daha sonra havuz arabirimini kullanarak bir atama işleci bir işaretçiye dönüştürülebilir.

##  <a name="getcontainer"></a>  CConnectionPoint::GetContainer

Almak için framework tarafından çağırılır `IConnectionPointContainer` için bağlantı noktası.

```
virtual LPCONNECTIONPOINTCONTAINER GetContainer();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, bir işaretçi; kapsayıcısı bulunmazsa null değerini DÖNDÜRÜR.

### <a name="remarks"></a>Açıklamalar

Bu işlev, genellikle begın_connectıon_part makrosu tarafından uygulanır.

##  <a name="getiid"></a>  CConnectionPoint::GetIID

Bir bağlantı noktasının arabirim kimliği almak için framework tarafından çağırılır.

```
virtual REFIID GetIID() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Bir başvuru bağlantı noktasının arabirim kimliği.

### <a name="remarks"></a>Açıklamalar

Bu bağlantı noktası için arabirim kimliği döndürmek için bu işleve geçersiz kılar.

##  <a name="getmaxconnections"></a>  CConnectionPoint::GetMaxConnections

Bağlantı bağlantı noktası tarafından desteklenen en fazla sayısını almak için framework tarafından çağırılır.

```
virtual int GetMaxConnections();
```

### <a name="return-value"></a>Dönüş Değeri

Bağlantı denetimi veya -1 sınırsız varsa, desteklenen maksimum sayısı.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama sınır belirten -1 döndürür.

Bu işlev, denetiminize bağlanabilir havuzlarını sayısını sınırlamak istiyorsanız geçersiz kılar.

##  <a name="getnextconnection"></a>  CConnectionPoint::GetNextConnection

Bağlantı öğe için bir işaretçi alır *pos*.

```
LPUNKNOWN GetNextConnection(POSITION& pos) const;
```

### <a name="parameters"></a>Parametreler

*POS*<br/>
Bir önceki tarafından döndürülen bir konum değeri bir başvuru belirtir `GetNextConnection` veya [GetStartPosition](#getstartposition) çağırın.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen bağlantı öğesi için bir işaretçi *pos*, veya NULL.

### <a name="remarks"></a>Açıklamalar

Bu işlev bağlantı eşlemesindeki tüm öğeleri arasında yineleme için kullanışlıdır. Yineleme, bir null değerlere bu işlevden döndürülen atlayın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCConnectionPoints#4](../../mfc/codesnippet/cpp/cconnectionpoint-class_3.cpp)]

##  <a name="getstartposition"></a>  CConnectionPoint::GetStartPosition

Harita yineleme, geçirilebilir bir konum değeri döndürerek başlar bir [GetNextConnection](#getnextconnection) çağırın.

```
POSITION GetStartPosition() const;
```

### <a name="return-value"></a>Dönüş Değeri

Harita yineleme için bir başlangıç konumunu belirten bir konum değeri; ya da bir eşlem boşsa, NULL.

### <a name="remarks"></a>Açıklamalar

Yineleme sırası tahmin edilebilir değil; Bu nedenle, "eşlem içindeki ilk öğeyi" özel bir önemi yoktur.

### <a name="example"></a>Örnek

  Örneğin bakın [CConnectionPoint::GetNextConnection](#getnextconnection).

##  <a name="onadvise"></a>  CConnectionPoint::OnAdvise

Framework tarafından bağlantı kurulduğunda ya çağrılmaz.

```
virtual void OnAdvise(BOOL bAdvise);
```

### <a name="parameters"></a>Parametreler

*bAdvise*<br/>
Bir bağlantı kurulur TRUE, Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, hiçbir şey yapmaz.

Bu işlev, bildirim havuzlarını bağlanın veya bağlantı noktanız kesmek istiyorsanız geçersiz kılar.

##  <a name="querysinkinterface"></a>  CConnectionPoint::QuerySinkInterface

İstenen havuz arabirim işaretçisi alır.

```
virtual HRESULT QuerySinkInterface(
    LPUNKNOWN pUnkSink,
    void** ppInterface);
```

### <a name="parameters"></a>Parametreler

*pUnkSink*<br/>
İstenen sonra havuz arabirimini tanımlayıcısı.

*ppInterface*<br/>
Tarafından tanımlanan bir arabirim işaretçisi için bir işaretçi *pUnkSink*. Nesne bu arabirimi desteklemiyorsa \* *ppInterface* NULL olarak ayarlandı.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

## <a name="see-also"></a>Ayrıca Bkz.

[CCmdTarget Sınıfı](../../mfc/reference/ccmdtarget-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)

