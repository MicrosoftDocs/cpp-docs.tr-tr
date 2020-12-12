---
description: 'Daha fazla bilgi edinin: CConnectionPoint sınıfı'
title: CConnectionPoint sınıfı
ms.date: 11/04/2016
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
ms.openlocfilehash: 62525428d8f9bf5303f379140837d75e53cbb387
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97227851"
---
# <a name="cconnectionpoint-class"></a>CConnectionPoint sınıfı

"Bağlantı noktası" olarak adlandırılan diğer OLE nesneleriyle iletişim kurmak için kullanılan özel bir arabirim türünü tanımlar.

## <a name="syntax"></a>Syntax

```
class CConnectionPoint : public CCmdTarget
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CConnectionPoint:: CConnectionPoint](#cconnectionpoint)|Bir `CConnectionPoint` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CConnectionPoint:: GetConnections](#getconnections)|Bir bağlantı eşlemesindeki tüm bağlantı noktalarını alır.|
|[CConnectionPoint:: GetContainer](#getcontainer)|Bağlantı eşlemesinin sahibi olan denetimin kapsayıcısını alır.|
|[CConnectionPoint:: GetIID](#getiid)|Bir bağlantı noktasının arabirim KIMLIĞINI alır.|
|[CConnectionPoint:: GetMaxConnections](#getmaxconnections)|Bir denetim tarafından desteklenen en fazla bağlantı noktası sayısını alır.|
|[CConnectionPoint:: GetNextConnection](#getnextconnection)|*POS 'ta* bağlantı öğesine bir işaretçi alır.|
|[CConnectionPoint:: GetStartPosition](#getstartposition)|Bir çağrıya geçirilebileceğini bir konum değeri döndürerek bir harita yinelemesi başlatır `GetNextConnection` .|
|[CConnectionPoint:: OnAdvise](#onadvise)|Bağlantı kurulurken veya koparmadan, Framework tarafından çağırılır.|
|[CConnectionPoint:: Querysinkınterface](#querysinkinterface)|İstenen havuz arabirimine bir işaretçi alır.|

## <a name="remarks"></a>Açıklamalar

Bir OLE denetiminin işlevselliğini uygulamak ve ortaya çıkarmak için kullanılan normal OLE arabirimlerinden farklı olarak, bağlantı noktası olayları ve değişiklik bildirimlerini başlatmak gibi diğer nesneler üzerinde eylem başlatabilecek bir giden arabirim uygular.

Bir bağlantı iki bölümden oluşur: "kaynak" adı verilen arabirimi çağıran nesne ve "Sink" adlı arabirimi uygulayan nesne. Bir bağlantı noktasını ortaya çıkaran bir kaynak, havuza bağlantı kurmasını sağlar. Kaynak nesne, bağlantı noktası mekanizmasıyla, bir dizi üye işlevleri havuzunun uygulamasına yönelik bir işaretçi alır. Örneğin, havuz tarafından uygulanan bir olayı tetikleyerek, kaynak havuzun uygulamasının uygun yöntemini çağırabilir.

Varsayılan olarak, bir `COleControl` türetilmiş sınıf iki bağlantı noktası uygular: biri olaylar için ve biri özellik değişikliği bildirimleri için. Bu bağlantılar sırasıyla olay başlatma için ve bir özellik değeri değiştiğinde bir havuza (örneğin, denetimin kapsayıcısı) bildirmek için kullanılır. Ayrıca, OLE denetimlerinin ek bağlantı noktaları uygulaması için de destek sağlanır. Denetim sınıfınıza uygulanan her ek bağlantı noktası için, bağlantı noktasını uygulayan bir "bağlantı bölümü" bildirmeniz gerekir. Bir veya daha fazla bağlantı noktası uygularsanız, denetim sınıfınıza tek bir "bağlantı haritası" da bildirmeniz gerekir.

Aşağıdaki örnek, iki kod parçasını içeren OLE denetimi için basit bir bağlantı haritasını ve bir bağlantı noktasını gösterir `Sample` : ilk bölüm bağlantı eşlemesini ve noktasını bildirir; ikincisi bu eşlemeyi ve noktasını uygular. İlk parça, Bölüm altındaki Denetim sınıfının bildirimine eklenir **`protected`** :

[!code-cpp[NVC_MFCConnectionPoints#7](../../mfc/codesnippet/cpp/cconnectionpoint-class_1.h)]

BEGIN_CONNECTION_PART ve END_CONNECTION_PART makroları, `XSampleConnPt` Bu bağlantı noktasını uygulayan gömülü bir sınıf (öğesinden türetilmiş `CConnectionPoint` ) bildirir. Herhangi bir üye işlevini geçersiz kılmak `CConnectionPoint` veya kendi üye işlevlerini eklemek istiyorsanız, bunları bu iki makro arasında bildirin. Örneğin, CONNECTION_IID makro `CConnectionPoint::GetIID` Bu iki makro arasında yerleştirildiğinde üye işlevini geçersiz kılar.

İkinci kod parçası uygulama dosyasına eklenir (. CPP). Bu kod, ek bağlantı noktasını içeren bağlantı haritasını uygular `SampleConnPt` :

[!code-cpp[NVC_MFCConnectionPoints#2](../../mfc/codesnippet/cpp/cconnectionpoint-class_2.cpp)]

Bu kod parçaları eklendikten sonra örnek OLE denetimi arabirim için bir bağlantı noktası sunar `ISampleSink` .

Genellikle bağlantı noktaları, aynı arabirime bağlı birden çok havuza yayınlanbilme özelliği olan "çok noktaya yayın" desteği sağlar. Aşağıdaki kod parçası, bir bağlantı noktasındaki her bir havuz arasında yineleme yaparak çok noktaya yayının nasıl gerçekleştirileceğini göstermektedir:

[!code-cpp[NVC_MFCConnectionPoints#4](../../mfc/codesnippet/cpp/cconnectionpoint-class_3.cpp)]

Bu örnek, bağlantı noktasındaki geçerli bağlantı kümesini `SampleConnPt` öğesine çağrısı ile alır `CConnectionPoint::GetConnections` . Daha sonra `ISampleSink::SinkFunc` her etkin bağlantı üzerinde bağlantılar ve çağrılar üzerinden yinelenir.

Kullanma hakkında daha fazla bilgi için `CConnectionPoint` bkz. [bağlantı noktaları](../../mfc/connection-points.md)makalesi.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`CConnectionPoint`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AfxDisp. h

## <a name="cconnectionpointcconnectionpoint"></a><a name="cconnectionpoint"></a> CConnectionPoint:: CConnectionPoint

Bir `CConnectionPoint` nesnesi oluşturur.

```
CConnectionPoint();
```

## <a name="cconnectionpointgetconnections"></a><a name="getconnections"></a> CConnectionPoint:: GetConnections

Bir bağlantı noktası için tüm etkin bağlantıları almak üzere bu işlevi çağırın.

```
const CPtrArray* GetConnections();
```

### <a name="return-value"></a>Dönüş Değeri

Etkin bağlantı dizisine yönelik bir işaretçi (havuz). Dizideki bazı işaretçiler NULL olabilir. Bu dizideki NULL olmayan her bir işaretçi, bir atama işleci kullanılarak havuz arabirimine yönelik bir işaretçiye güvenle dönüştürülebilir.

## <a name="cconnectionpointgetcontainer"></a><a name="getcontainer"></a> CConnectionPoint:: GetContainer

Bağlantı noktası için öğesini almak üzere Framework tarafından çağırılır `IConnectionPointContainer` .

```
virtual LPCONNECTIONPOINTCONTAINER GetContainer();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, kapsayıcı işaretçisi; Aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Bu işlev genellikle BEGIN_CONNECTION_PART makrosu tarafından uygulanır.

## <a name="cconnectionpointgetiid"></a><a name="getiid"></a> CConnectionPoint:: GetIID

Bir bağlantı noktasının arabirim KIMLIĞINI almak için Framework tarafından çağırılır.

```
virtual REFIID GetIID() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Bağlantı noktasının arabirim KIMLIĞINE bir başvuru.

### <a name="remarks"></a>Açıklamalar

Bu bağlantı noktasının arabirim KIMLIĞINI döndürmek için bu işlevi geçersiz kılın.

## <a name="cconnectionpointgetmaxconnections"></a><a name="getmaxconnections"></a> CConnectionPoint:: GetMaxConnections

Bağlantı noktası tarafından desteklenen maksimum bağlantı sayısını almak için Framework tarafından çağırılır.

```
virtual int GetMaxConnections();
```

### <a name="return-value"></a>Dönüş Değeri

Denetim tarafından desteklenen en fazla bağlantı sayısı veya sınır yoksa-1.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, sınır olmadığını gösteren-1 döndürür.

Denetimi bağlayabileceğiniz havuz sayısını sınırlamak istiyorsanız bu işlevi geçersiz kılın.

## <a name="cconnectionpointgetnextconnection"></a><a name="getnextconnection"></a> CConnectionPoint:: GetNextConnection

*POS 'ta* bağlantı öğesine bir işaretçi alır.

```
LPUNKNOWN GetNextConnection(POSITION& pos) const;
```

### <a name="parameters"></a>Parametreler

*'un*<br/>
Önceki `GetNextConnection` veya [GetStartPosition](#getstartposition) ÇAĞRıSıYLA döndürülen bir konum değerine bir başvuru belirtir.

### <a name="return-value"></a>Dönüş Değeri

*POS* veya null tarafından belirtilen bağlantı öğesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu işlev, bağlantı eşlemesindeki tüm öğeler arasında yineleme için en yararlı seçenektir. Yinelenirken, bu işlevden döndürülen tüm null değerleri atlayın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCConnectionPoints#4](../../mfc/codesnippet/cpp/cconnectionpoint-class_3.cpp)]

## <a name="cconnectionpointgetstartposition"></a><a name="getstartposition"></a> CConnectionPoint:: GetStartPosition

Bir [GetNextConnection](#getnextconnection) çağrısına GEÇIRILEBILECEK bir konum değeri döndürerek bir harita yinelemesi başlatır.

```
POSITION GetStartPosition() const;
```

### <a name="return-value"></a>Dönüş Değeri

Haritayı yineleme için başlangıç konumunu belirten bir konum değeri; veya eşleme boşsa NULL.

### <a name="remarks"></a>Açıklamalar

Yineleme sırası öngörülebilir değil; Bu nedenle, "haritadaki ilk öğe" özel bir anlam içermez.

### <a name="example"></a>Örnek

  [CConnectionPoint:: GetNextConnection](#getnextconnection)örneğine bakın.

## <a name="cconnectionpointonadvise"></a><a name="onadvise"></a> CConnectionPoint:: OnAdvise

Bir bağlantı kurulurken veya kesiliyorsa Framework tarafından çağırılır.

```
virtual void OnAdvise(BOOL bAdvise);
```

### <a name="parameters"></a>Parametreler

*Rozzden*<br/>
Bağlantı kurulduysa doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama hiçbir şey yapmaz.

Havuzlar bağlantı noktanma bağlandığında veya bağlantısı kesildiğinde bildirim istiyorsanız bu işlevi geçersiz kılın.

## <a name="cconnectionpointquerysinkinterface"></a><a name="querysinkinterface"></a> CConnectionPoint:: Querysinkınterface

İstenen havuz arabirimine bir işaretçi alır.

```
virtual HRESULT QuerySinkInterface(
    LPUNKNOWN pUnkSink,
    void** ppInterface);
```

### <a name="parameters"></a>Parametreler

*pUnkSink*<br/>
İstenen havuz arabiriminin tanımlayıcısı.

*ppInterface*<br/>
*PUnkSink* tarafından tanımlanan arabirim işaretçisine yönelik bir işaretçi. Nesne bu arabirimi desteklemiyorsa, \* *PPıNTERFACE* null olarak ayarlanır.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

## <a name="see-also"></a>Ayrıca bkz.

[CCmdTarget sınıfı](../../mfc/reference/ccmdtarget-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)
