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
ms.openlocfilehash: d892ea225e3b1c1089447587eb808e56370bbb69
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36952228"
---
# <a name="cconnectionpoint-class"></a>CConnectionPoint sınıfı
Bir özel tür "bağlantı noktası." olarak adlandırılan diğer OLE nesneleri ile iletişim kurmak için kullanılan arabirim tanımlar  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CConnectionPoint : public CCmdTarget  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CConnectionPoint::CConnectionPoint](#cconnectionpoint)|Oluşturan bir `CConnectionPoint` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CConnectionPoint::GetConnections](#getconnections)|Bir bağlantı eşlemindeki tüm bağlantı noktaları alır.|  
|[CConnectionPoint::GetContainer](#getcontainer)|Bağlantı eşlemine sahip denetim kapsayıcısını alır.|  
|[CConnectionPoint::GetIID](#getiid)|Bir bağlantı noktası arabirimi Kimliğini alır.|  
|[CConnectionPoint::GetMaxConnections](#getmaxconnections)|Bağlantı noktaları bir denetim tarafından desteklenen maksimum sayısını alır.|  
|[CConnectionPoint::GetNextConnection](#getnextconnection)|Konumundaki bağlantı öğe için bir işaretçi alır *pos*.|  
|[CConnectionPoint::GetStartPosition](#getstartposition)|Harita yineleme döndürerek başlatır bir **konumu** için geçirilen değer bir `GetNextConnection` çağırın.|  
|[CConnectionPoint::OnAdvise](#onadvise)|Oluşturma veya bağlantılarını kesme çerçevesi tarafından çağrılır.|  
|[CConnectionPoint::QuerySinkInterface](#querysinkinterface)|İstenen havuz arayüzü için bir işaretçi alır.|  
  
## <a name="remarks"></a>Açıklamalar  
 OLE denetim işlevselliğini kullanıma sunabilir ve uygulanması için kullanılan normal OLE arabirimleri, bir bağlantı noktası Eylemler olaylarını tetikleme gibi diğer nesneler üzerinde başlatmak ve bildirimleri değiştirin yapabiliyor bir giden arabirimini uygular.  
  
 Bir bağlantı iki bölümden oluşur: "kaynak" ve arabirimini uygulayan nesne adında arabirimi çağırma nesnesi adında "havuz." Bir bağlantı noktası göstererek bir kaynak havuzlarını kendisini bağlantı sağlar. Bağlantı noktası mekanizması üye işlevleri kümesi havuz 's uygulaması için bir işaretçi bir kaynak nesnesi alır. Örneğin, havuzu tarafından uygulanan bir olay tetikleyin için kaynak havuzu 's uygulama uygun yöntemini çağırabilirsiniz.  
  
 Varsayılan olarak, bir `COleControl`-türetilmiş sınıf uygulayan iki bağlantı noktası: olaylar için diğeri özelliği için değişiklik bildirimleri. Bu bağlantılar kullanılır, sırasıyla olay tetikleme ve ne zaman bir havuz (örneğin, denetimin kapsayıcısı) bilgilendirmek için bir özellik değeri değiştirildi. Destek OLE denetimlerinin ek bağlantı noktaları uygulamak için de sağlanır. Denetim sınıfınızda uygulanan her ek bağlantı noktası için "bağlantı noktası uygulayan bir bağlantı bölümünü" bildirmeniz gerekir. Bir veya daha fazla bağlantı noktaları uygularsanız, ayrıca tek bir "bağlantı eşlemesinde" Denetim sınıfınıza bildirmeniz gerekir.  
  
 Aşağıdaki örnek, bir basit bağlantı harita ve bir bağlantı noktası için gösterir `Sample` OLE denetimi, kod iki parçalarını oluşan: ilk bölümü noktası ve bağlantı harita bildirir; bu harita ve noktası ikinci uygular. İlk parça denetim sınıfı bildirimi içine altında eklenir `protected` bölümü:  
  
 [!code-cpp[NVC_MFCConnectionPoints#7](../../mfc/codesnippet/cpp/cconnectionpoint-class_1.h)]  
  
 Begın_connectıon_part ve end_connectıon_part makroları katıştırılmış bir sınıf bildirme `XSampleConnPt` (türetilmiş `CConnectionPoint`), bu belirli bağlantı noktası uygular. Herhangi bir geçersiz kılmak istiyorsanız `CConnectionPoint` üye işlevleri veya kendi üye işlevleri eklemek için bu iki makrolar arasında bildirin. Örneğin, connectıon_ııd makrosu geçersiz kılmaları `CConnectionPoint::GetIID` bu iki makrolar arasında yerleştirildiğinde üye işlevi.  
  
 İkinci kod parçası uygulama dosyasına eklenir (. CPP) denetim sınıfınızın. Bu kod ek bağlantı noktası'nı içeren bağlantı harita uygulayan `SampleConnPt`:  
  
 [!code-cpp[NVC_MFCConnectionPoints#2](../../mfc/codesnippet/cpp/cconnectionpoint-class_2.cpp)]  
  
 Bu kod parçaları ekledikten sonra örnek OLE denetimi için bir bağlantı noktası sunan `ISampleSink` arabirimi.  
  
 Normalde, bağlantı noktaları aynı arabirime bağlı birden çok havuzlarını yayın özelliği "noktaya" destekler. Aşağıdaki kod parçası, çok noktaya yayın bağlantı noktası üzerinde her havuz üzerinden yineleme tarafından gerçekleştirmek gösterilmiştir:  
  
 [!code-cpp[NVC_MFCConnectionPoints#4](../../mfc/codesnippet/cpp/cconnectionpoint-class_3.cpp)]  
  
 Bu örnek, üzerinde bağlantıları geçerli kümesini alır. `SampleConnPt` çağrısıyla bağlantı noktası `CConnectionPoint::GetConnections`. Ardından çağrıları ve bağlantıları tekrarlanan `ISampleSink::SinkFunc` her etkin bir bağlantı üzerinde.  
  
 Kullanma hakkında daha fazla bilgi için `CConnectionPoint`, makaleye bakın [bağlantı noktaları](../../mfc/connection-points.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CConnectionPoint`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdisp.h  
  
##  <a name="cconnectionpoint"></a>  CConnectionPoint::CConnectionPoint  
 Oluşturan bir `CConnectionPoint` nesnesi.  
  
```  
CConnectionPoint();
```  
  
##  <a name="getconnections"></a>  CConnectionPoint::GetConnections  
 Bir bağlantı noktası için tüm etkin bağlantılar almak için bu işlevini çağırın.  
  
```  
const CPtrArray* GetConnections();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir dizi etkin bağlantılar (iç havuzlar) için bir işaretçi. Bazı işaretçiler dizideki NULL olabilir. Dizideki her boş olmayan işaretçi güvenli bir şekilde atama işleci kullanarak havuz arabirimi için bir işaretçi dönüştürülebilir.  
  
##  <a name="getcontainer"></a>  CConnectionPoint::GetContainer  
 Alınacak çerçevesi tarafından çağrılır **IConnectionPointContainer** bağlantı noktası için.  
  
```  
virtual LPCONNECTIONPOINTCONTAINER GetContainer();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, bir işaretçi kapsayıcıya; Aksi takdirde **NULL**.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev genel begın_connectıon_part makrosu tarafından uygulanır.  
  
##  <a name="getiid"></a>  CConnectionPoint::GetIID  
 Bir bağlantı noktası arabirimi Kimliğini almak için çerçevesi tarafından çağrılır.  
  
```  
virtual REFIID GetIID() = 0;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bağlantı noktasının arabirimi kimliği başvurusu  
  
### <a name="remarks"></a>Açıklamalar  
 Bu bağlantı noktası için arabirim kimliği döndürmek için bu işleve geçersiz kılar.  
  
##  <a name="getmaxconnections"></a>  CConnectionPoint::GetMaxConnections  
 Bağlantıları bağlantı noktası tarafından desteklenen en fazla sayısını almak üzere çerçevesi tarafından çağrılır.  
  
```  
virtual int GetMaxConnections();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sınır olmadığını denetimi ya da -1 tarafından desteklenen bağlantılarının maksimum sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulama sınır belirten -1 döndürür.  
  
 Denetiminize bağlanabilir havuzlarını sayısını sınırlamak istiyorsanız, bu işlev geçersiz kılar.  
  
##  <a name="getnextconnection"></a>  CConnectionPoint::GetNextConnection  
 Konumundaki bağlantı öğe için bir işaretçi alır *pos*.  
  
```  
LPUNKNOWN GetNextConnection(POSITION& pos) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *POS*  
 Bir başvuru belirtir bir **konumu** önceki tarafından döndürülen değer `GetNextConnection` veya [GetStartPosition](#getstartposition) çağırın.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen bağlantı öğesi için bir işaretçi *pos*, veya NULL.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev bağlantısı eşlemindeki tüm öğeleri üzerinden yineleme için kullanışlıdır. Yineleme sırasında bu işlevinden döndürülen null atlanacak.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCConnectionPoints#4](../../mfc/codesnippet/cpp/cconnectionpoint-class_3.cpp)]  
  
##  <a name="getstartposition"></a>  CConnectionPoint::GetStartPosition  
 Harita yineleme döndürerek başlatır bir **konumu** için geçirilen değer bir [GetNextConnection](#getnextconnection) çağırın.  
  
```  
POSITION GetStartPosition() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A **konumu** ; harita yineleme için bir başlangıç konumunu belirten değer veya **NULL** harita boşsa.  
  
### <a name="remarks"></a>Açıklamalar  
 Yineleme sırası tahmin edilebilir değil; Bu nedenle, "ilk öğenin" eşlemesindeki özel bir önemi yoktur.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CConnectionPoint::GetNextConnection](#getnextconnection).  
  
##  <a name="onadvise"></a>  CConnectionPoint::OnAdvise  
 Bağlantı çerçevesi tarafından kurulan veya bozuk çağrılmaz.  
  
```  
virtual void OnAdvise(BOOL bAdvise);
```  
  
### <a name="parameters"></a>Parametreler  
 *bAdvise*  
 **DOĞRU**, bağlantı kurulan; Aksi takdirde **FALSE**.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulama hiçbir şey yapmaz.  
  
 Havuzlarını bağlanmak veya bağlantı noktasından bağlantı kesme zaman bildirim istiyorsanız, bu işlev geçersiz kılar.  
  
##  <a name="querysinkinterface"></a>  CConnectionPoint::QuerySinkInterface  
 İstenen havuz arayüzü için bir işaretçi alır.  
  
```  
virtual HRESULT QuerySinkInterface(
    LPUNKNOWN pUnkSink,  
    void** ppInterface);
```  
  
### <a name="parameters"></a>Parametreler  
 *pUnkSink*  
 İstenen havuz arabirimi tanımlayıcısı.  
  
 *ppInterface*  
 Arabirim işaretçisi ile tanımlanan bir işaretçi *pUnkSink*. Nesne bu arabirim desteklemiyorsa \* *ppInterface* ayarlanır **NULL**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CCmdTarget sınıfı](../../mfc/reference/ccmdtarget-class.md)   
 [Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)

