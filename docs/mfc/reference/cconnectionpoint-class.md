---
title: CConnectionPoint Sınıfı
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
ms.openlocfilehash: ce72c156ab31b742a42d2960923fc56afff656c0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369435"
---
# <a name="cconnectionpoint-class"></a>CConnectionPoint Sınıfı

"Bağlantı noktası" adı verilen diğer OLE nesneleri ile iletişim kurmak için kullanılan özel bir arabirim türünü tanımlar.

## <a name="syntax"></a>Sözdizimi

```
class CConnectionPoint : public CCmdTarget
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CConnectionPoint::CConnectionPoint](#cconnectionpoint)|Bir `CConnectionPoint` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CConnectionPoint::Bağlantı Alma](#getconnections)|Bağlantı haritasındaki tüm bağlantı noktalarını alır.|
|[CConnectionPoint::GetContainer](#getcontainer)|Bağlantı eşleninin sahibi olan denetimin kapsayıcısını alır.|
|[CConnectionPoint::GetIID](#getiid)|Bağlantı noktasının arabirim kimliğini alır.|
|[CConnectionPoint::GetMaxConnections](#getmaxconnections)|Denetim tarafından desteklenen maksimum bağlantı noktası sayısını alır.|
|[CConnectionPoint::GetNextConnection](#getnextconnection)|*Pos'taki*bağlantı öğesiiçin bir işaretçi alır.|
|[CConnectionPoint::GetStartPosition](#getstartposition)|`GetNextConnection` Bir çağrıya geçirilebilen bir POSITION değerini döndürerek bir harita yinelemesini başlatır.|
|[CConnectionPoint::OnAdvise](#onadvise)|Bağlantıları kurarken veya kırarken çerçeve tarafından çağrılır.|
|[CConnectionPoint::QuerySinkInterface](#querysinkinterface)|İstenen lavabo arabirimi için bir işaretçi alır.|

## <a name="remarks"></a>Açıklamalar

OLE denetiminin işlevselliğini uygulamak ve ortaya çıkarmak için kullanılan normal OLE arabirimlerinin aksine, bir bağlantı noktası, olayları başlatma ve bildirimleri değiştirme gibi diğer nesneler üzerinde eylem başlatabilen giden bir arabirim uygular.

Bağlantı iki bölümden oluşur: arabirimi çağıran nesne, "kaynak" olarak adlandırılır ve arabirimi uygulayan nesne "lavabo" olarak adlandırılır. Bir bağlantı noktası açığa çıkararak, bir kaynak lavaboların kendisine bağlantı kurmasına olanak tanır. Bağlantı noktası mekanizması sayesinde, bir kaynak nesne, bir üye işlevler kümesinin lavabonun uygulanması için bir işaretçi alır. Örneğin, lavabo tarafından uygulanan bir olayı ateşlemek için kaynak, lavabonun uygulanmasının uygun yöntemini çağırabilir.

Varsayılan olarak, `COleControl`türetilmiş bir sınıf iki bağlantı noktası uygular: biri olaylar için, diğeri özellik değişikliği bildirimleri için. Bu bağlantılar, sırasıyla, olay ateşleme ve bir özellik değeri değiştiğinde bir lavaboyu (örneğin, denetimin kapsayıcısı) bildirmek için kullanılır. Ek bağlantı noktaları uygulamak için OLE denetimleri için destek de sağlanır. Denetim sınıfınızda uygulanan her ek bağlantı noktası için, bağlantı noktasını uygulayan bir "bağlantı parçası" bildirmeniz gerekir. Bir veya daha fazla bağlantı noktası uygularsanız, denetim sınıfınızda tek bir "bağlantı eşlemi" de bildirmeniz gerekir.

Aşağıdaki örnek, iki kod parçasından oluşan `Sample` basit bir bağlantı eşlemi ve OLE denetimi için bir bağlantı noktasını gösterir: ilk bölüm bağlantı eşlemi ve noktasını bildirir; ikincisi bu haritayı ve noktayı uygular. İlk **parça, korumalı** bölümün altına denetim sınıfının bildirimine eklenir:

[!code-cpp[NVC_MFCConnectionPoints#7](../../mfc/codesnippet/cpp/cconnectionpoint-class_1.h)]

BEGIN_CONNECTION_PART ve END_CONNECTION_PART makroları, `XSampleConnPt` bu özel `CConnectionPoint`bağlantı noktasını uygulayan gömülü bir sınıf (türetilmiş) bildirir. Herhangi bir `CConnectionPoint` üye işlevi geçersiz kılmak veya kendi üye işlevlerieklemek istiyorsanız, bunları bu iki makro arasında bildirin. Örneğin, CONNECTION_IID makrosu, `CConnectionPoint::GetIID` bu iki makro arasına yerleştirildiğinde üye işlevi geçersiz kılar.

İkinci kod parçası uygulama dosyasına eklenir (. CPP) kontrol sınıfının. Bu kod, ek bağlantı noktasını içeren bağlantı `SampleConnPt`eşlemi uygular:

[!code-cpp[NVC_MFCConnectionPoints#2](../../mfc/codesnippet/cpp/cconnectionpoint-class_2.cpp)]

Bu kod parçaları yerleştirildikten sonra Örnek OLE denetimi `ISampleSink` arabirim için bir bağlantı noktasını ortaya çıkarır.

Genellikle, bağlantı noktaları aynı arabirime bağlı birden çok lavaboya yayın yapma olanağı olan "çok döküm"u destekler. Aşağıdaki kod parçası, bir bağlantı noktasında her lavabo aracılığıyla yineleyerek çok döküm gerçekleştirmek için nasıl gösterir:

[!code-cpp[NVC_MFCConnectionPoints#4](../../mfc/codesnippet/cpp/cconnectionpoint-class_3.cpp)]

Bu örnek, `SampleConnPt` bağlantı noktasındaki geçerli bağlantı kümesini bir `CConnectionPoint::GetConnections`çağrı ile alır. Daha sonra bağlantılar aracılığıyla yineler `ISampleSink::SinkFunc` ve her etkin bağlantıyı çağırır.

Kullanma `CConnectionPoint`hakkında daha fazla bilgi için [Bağlantı Noktaları](../../mfc/connection-points.md)makalesine bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

`CConnectionPoint`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdisp.h

## <a name="cconnectionpointcconnectionpoint"></a><a name="cconnectionpoint"></a>CConnectionPoint::CConnectionPoint

Bir `CConnectionPoint` nesne inşa eder.

```
CConnectionPoint();
```

## <a name="cconnectionpointgetconnections"></a><a name="getconnections"></a>CConnectionPoint::Bağlantı Alma

Bir bağlantı noktası için tüm etkin bağlantıları almak için bu işlevi arayın.

```
const CPtrArray* GetConnections();
```

### <a name="return-value"></a>Dönüş Değeri

Etkin bağlantılar (lavabolar) dizisi için bir işaretçi. Dizideki işaretçilerden bazıları NULL olabilir. Bu dizideki NULL olmayan her işaretçi, bir döküm işleci kullanılarak güvenli bir şekilde lavabo arabirimine bir işaretçiye dönüştürülebilir.

## <a name="cconnectionpointgetcontainer"></a><a name="getcontainer"></a>CConnectionPoint::GetContainer

Bağlantı noktası `IConnectionPointContainer` için almak için çerçeve tarafından çağrılır.

```
virtual LPCONNECTIONPOINTCONTAINER GetContainer();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, kapsayıcıya bir işaretçi; aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Bu işlev genellikle BEGIN_CONNECTION_PART makro tarafından uygulanır.

## <a name="cconnectionpointgetiid"></a><a name="getiid"></a>CConnectionPoint::GetIID

Bir bağlantı noktasının arabirim kimliğini almak için çerçeve tarafından çağrılır.

```
virtual REFIID GetIID() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Bağlantı noktasının arayüz kimliğine başvuru.

### <a name="remarks"></a>Açıklamalar

Bu bağlantı noktası için arabirim kimliğini döndürmek için bu işlevi geçersiz kılın.

## <a name="cconnectionpointgetmaxconnections"></a><a name="getmaxconnections"></a>CConnectionPoint::GetMaxConnections

Bağlantı noktası tarafından desteklenen maksimum bağlantı sayısını almak için çerçeve tarafından çağrılır.

```
virtual int GetMaxConnections();
```

### <a name="return-value"></a>Dönüş Değeri

Denetim tarafından desteklenen maksimum bağlantı sayısı veya limit yoksa -1.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama -1 döndürür, sınır belirterek.

Denetiminize bağlanabilecek lavabo sayısını sınırlamak istiyorsanız bu işlevi geçersiz kılın.

## <a name="cconnectionpointgetnextconnection"></a><a name="getnextconnection"></a>CConnectionPoint::GetNextConnection

*Pos'taki*bağlantı öğesiiçin bir işaretçi alır.

```
LPUNKNOWN GetNextConnection(POSITION& pos) const;
```

### <a name="parameters"></a>Parametreler

*Pos*<br/>
Bir önceki `GetNextConnection` veya [GetStartPosition](#getstartposition) çağrısı yla döndürülen bir POSITION değerine başvuru belirtir.

### <a name="return-value"></a>Dönüş Değeri

*Pos*veya NULL tarafından belirtilen bağlantı öğesiiçin bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu işlev, bağlantı haritasındaki tüm öğeleri yinelebilmek için en yararlıdır. Yinelendiğinde, bu işlevden döndürülen tüm NULL'leri atlayın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCConnectionPoints#4](../../mfc/codesnippet/cpp/cconnectionpoint-class_3.cpp)]

## <a name="cconnectionpointgetstartposition"></a><a name="getstartposition"></a>CConnectionPoint::GetStartPosition

[GetNextConnection](#getnextconnection) çağrısına geçirilebilen bir POSITION değeri döndürerek bir harita yinelemesini başlatır.

```
POSITION GetStartPosition() const;
```

### <a name="return-value"></a>Dönüş Değeri

Haritayı yineleyen bir başlangıç konumunu gösteren bir KONUM değeri; veya harita boşsa NULL.

### <a name="remarks"></a>Açıklamalar

Yineleme sırası tahmin edilebilir değildir; bu nedenle, "haritadaki ilk öğenin" özel bir önemi yoktur.

### <a name="example"></a>Örnek

  CConnectionPoint örneğine [bakın:GetNextConnection](#getnextconnection).

## <a name="cconnectionpointonadvise"></a><a name="onadvise"></a>CConnectionPoint::OnAdvise

Bir bağlantı kurulduğunda veya kırılırken çerçeve tarafından çağrılır.

```
virtual void OnAdvise(BOOL bAdvise);
```

### <a name="parameters"></a>Parametreler

*bAdvise*<br/>
DOĞRU, bir bağlantı kurulurise; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama hiçbir şey yapmaz.

Lavabolar bağlantı noktanıza bağlandığında veya bağlantı noktanızı kestiğinizde bildirim istiyorsanız bu işlevi geçersiz kılın.

## <a name="cconnectionpointquerysinkinterface"></a><a name="querysinkinterface"></a>CConnectionPoint::QuerySinkInterface

İstenen lavabo arabirimi için bir işaretçi alır.

```
virtual HRESULT QuerySinkInterface(
    LPUNKNOWN pUnkSink,
    void** ppInterface);
```

### <a name="parameters"></a>Parametreler

*pUnkSink*<br/>
İstenmekte olan lavabo arabiriminin tanımlayıcısı.

*ppArayüz*<br/>
*pUnkSink*tarafından tanımlanan arabirim işaretçisi için bir işaretçi. Nesne bu arabirimi desteklemiyorsa, \* *ppInterface* NULL olarak ayarlanır.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

## <a name="see-also"></a>Ayrıca bkz.

[CCmdTarget Sınıfı](../../mfc/reference/ccmdtarget-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
