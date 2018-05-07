---
title: COleDataObject sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleDataObject
- AFXOLE/COleDataObject
- AFXOLE/COleDataObject::COleDataObject
- AFXOLE/COleDataObject::Attach
- AFXOLE/COleDataObject::AttachClipboard
- AFXOLE/COleDataObject::BeginEnumFormats
- AFXOLE/COleDataObject::Detach
- AFXOLE/COleDataObject::GetData
- AFXOLE/COleDataObject::GetFileData
- AFXOLE/COleDataObject::GetGlobalData
- AFXOLE/COleDataObject::GetNextFormat
- AFXOLE/COleDataObject::IsDataAvailable
- AFXOLE/COleDataObject::Release
dev_langs:
- C++
helpviewer_keywords:
- COleDataObject [MFC], COleDataObject
- COleDataObject [MFC], Attach
- COleDataObject [MFC], AttachClipboard
- COleDataObject [MFC], BeginEnumFormats
- COleDataObject [MFC], Detach
- COleDataObject [MFC], GetData
- COleDataObject [MFC], GetFileData
- COleDataObject [MFC], GetGlobalData
- COleDataObject [MFC], GetNextFormat
- COleDataObject [MFC], IsDataAvailable
- COleDataObject [MFC], Release
ms.assetid: d1cc84be-2e1c-4bb3-a8a0-565eb08aaa34
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e9cd159597440dfb55bbe8abe147623096cdf449
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="coledataobject-class"></a>COleDataObject sınıfı
Veri aktarımları ile sürükle ve bırak, Pano veya katıştırılmış OLE öğeyi çeşitli biçimlerde verileri almak için kullanılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class COleDataObject  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleDataObject::COleDataObject](#coledataobject)|Oluşturan bir `COleDataObject` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleDataObject::Attach](#attach)|Belirtilen OLE veri nesnesine ekler `COleDataObject`.|  
|[COleDataObject::AttachClipboard](#attachclipboard)|Üzerinde Pano veri nesnesi ekler.|  
|[COleDataObject::BeginEnumFormats](#beginenumformats)|Bir veya daha sonraki hazırlar `GetNextFormat` çağrıları.|  
|[COleDataObject::Detach](#detach)|İlişkili ayırır `IDataObject` nesnesi.|  
|[COleDataObject::GetData](#getdata)|Belirtilen biçime bağlı OLE veri nesnesinde verileri kopyalar.|  
|[COleDataObject::GetFileData](#getfiledata)|Ekli OLE veri nesnesine gelen verileri kopyalar bir `CFile` belirtilen biçiminde işaretçi.|  
|[COleDataObject::GetGlobalData](#getglobaldata)|Ekli OLE veri nesnesine gelen verileri kopyalar bir `HGLOBAL` belirtilen biçiminde.|  
|[COleDataObject::GetNextFormat](#getnextformat)|Sonraki veri biçimi döndürür.|  
|[COleDataObject::IsDataAvailable](#isdataavailable)|Verileri belirtilen biçimde kullanılabilir olup olmadığını denetler.|  
|[COleDataObject::Release](#release)|Ayırır ve ilişkili serbest `IDataObject` nesnesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 `COleDataObject` bir taban sınıfı yok.  
  
 Bu tür veri aktarımları, bir kaynak ve hedef içerir. Veri kaynağı bir nesnenin uygulanan [COleDataSource](../../mfc/reference/coledatasource-class.md) sınıfı. Her bir hedef uygulama içinde bırakılan veri veya panodan, bir nesneyi yapıştırma işlemi gerçekleştirmek için sorulan `COleDataObject` sınıfı oluşturulmalıdır.  
  
 Bu sınıf verileri belirtilen biçimde var olup olmadığını belirlemenizi sağlar. Ayrıca kullanılabilir veri biçimleri listeleme veya belirli bir biçim kullanılabilir olup olmadığını denetleyin ve tercih edilen biçimindeki verileri almak. Nesne alma kullanımı gibi birçok farklı yöntemle, gerçekleştirilebilir bir [CFile](../../mfc/reference/cfile-class.md), bir `HGLOBAL`, veya bir **STGMEDIUM** yapısı.  
  
 Daha fazla bilgi için bkz: [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) Windows SDK'sındaki yapısı.  
  
 Veri nesneleri, uygulamanızda kullanma hakkında daha fazla bilgi için bkz: [veri nesneleri ve veri kaynakları (OLE)](../../mfc/data-objects-and-data-sources-ole.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `COleDataObject`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxole.h  
  
##  <a name="attach"></a>  COleDataObject::Attach  
 İlişkilendirmek için bu işlevi çağırmak `COleDataObject` nesnesi ile OLE veri nesnesi.  
  
```  
void Attach(
    LPDATAOBJECT lpDataObject,  
    BOOL bAutoRelease = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpDataObject*  
 OLE veri nesnesi noktalarına.  
  
 `bAutoRelease`  
 **DOĞRU** OLE veri nesnesi olacaksa, ne zaman serbest `COleDataObject` nesnesidir yok; Aksi takdirde **FALSE**.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421) Windows SDK'sındaki.  
  
##  <a name="attachclipboard"></a>  COleDataObject::AttachClipboard  
 Şu anda açık olan Pano veri nesnesi eklemek için bu işlevi çağırmak `COleDataObject` nesnesi.  
  
```  
BOOL AttachClipboard();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
  
> [!NOTE]
>  Bu veri nesnesi serbest kadar bu işlev çağırma Pano kilitler. Veri nesnesi için yıkıcı de serbest `COleDataObject`. Daha fazla bilgi için bkz: [OpenClipboard](http://msdn.microsoft.com/library/windows/desktop/ms649048) ve [CloseClipboard](http://msdn.microsoft.com/library/windows/desktop/ms649035) Win32 belgelerine içinde.  
  
##  <a name="beginenumformats"></a>  COleDataObject::BeginEnumFormats  
 Sonraki çağrılar için hazırlamak için bu işlevi çağırmak `GetNextFormat` öğesinden veri biçimleri listesini almak için.  
  
```  
void BeginEnumFormats();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrı sonra `BeginEnumFormats`, bu veri nesnesi tarafından desteklenen ilk biçimi konumunu depolanır. Art arda çağrılar `GetNextFormat` veri nesnesi kullanılabilir biçimlerde listesini numaralandırır.  
  
 Belirli bir biçimde veri kullanılabilirliğini denetlemek için kullanın [COleDataObject::IsDataAvailable](#isdataavailable).  
  
 Daha fazla bilgi için bkz: [IDataObject::EnumFormatEtc](http://msdn.microsoft.com/library/windows/desktop/ms683979) Windows SDK'sındaki.  
  
##  <a name="coledataobject"></a>  COleDataObject::COleDataObject  
 Oluşturan bir `COleDataObject` nesnesi.  
  
```  
COleDataObject();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrı [COleDataObject::Attach](#attach) veya [COleDataObject::AttachClipboard](#attachclipboard) diğer çağırmadan önce yapılmalıdır `COleDataObject` işlevleri.  
  
> [!NOTE]
>  Parametrelerden biri sürükle ve bırak işleyicileri için bir işaretçi olduğundan bir `COleDataObject`, sürükle ve bırak desteklemek için bu oluşturucuyu çağırmak için gerek yoktur.  
  
##  <a name="detach"></a>  COleDataObject::Detach  
 Kullanımdan çıkarmak için bu işlevi çağırmak `COleDataObject` nesnesinden verileri nesne serbest olmadan, ilişkili OLE veri nesnesi.  
  
```  
LPDATAOBJECT Detach();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ayrıldı OLE veri nesnesi için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getdata"></a>  COleDataObject::GetData  
 Belirtilen biçim öğesinden verileri almak için bu işlevini çağırın.  
  
```  
BOOL GetData(
    CLIPFORMAT cfFormat,  
    LPSTGMEDIUM lpStgMedium,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `cfFormat`  
 Veri döndürülecek olan biçimi. Bu parametre bir ön tanımlı Pano biçimleri veya yerel Windows tarafından döndürülen değer olabilir [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) işlevi.  
  
 `lpStgMedium`  
 İşaret eden bir [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) veri alacak yapısı.  
  
 `lpFormatEtc`  
 İşaret eden bir [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) veri olduğu döndürülecek biçimi açıklayan yapısı. Pano biçimi tarafından belirtilen ötesinde ek biçim bilgilerini belirtmek istiyorsanız, bu parametre için bir değer sağlayın `cfFormat`. Eğer öyleyse **NULL**, diğer alanları için varsayılan değerler kullanılır **FORMATETC** yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [IDataObject::GetData](http://msdn.microsoft.com/library/windows/desktop/ms678431), [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812), ve [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Windows SDK'sındaki.  
  
 Daha fazla bilgi için bkz: [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) Windows SDK'sındaki.  
  
##  <a name="getfiledata"></a>  COleDataObject::GetFileData  
 Oluşturmak için bu işlevi çağırmak bir `CFile` veya `CFile`-türetilen nesnesini ve belirtilen biçime verileri almak için bir `CFile` işaretçi.  
  
```  
CFile* GetFileData(
    CLIPFORMAT cfFormat,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `cfFormat`  
 Veri döndürülecek olan biçimi. Bu parametre bir ön tanımlı Pano biçimleri veya yerel Windows tarafından döndürülen değer olabilir [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) işlevi.  
  
 `lpFormatEtc`  
 İşaret eden bir [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) veri olduğu döndürülecek biçimi açıklayan yapısı. Pano biçimi tarafından belirtilen ötesinde ek biçim bilgilerini belirtmek istiyorsanız, bu parametre için bir değer sağlayın `cfFormat`. Eğer öyleyse **NULL**, diğer alanları için varsayılan değerler kullanılır **FORMATETC** yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşaretçi yeni `CFile` veya `CFile`-türetilen nesne verilerini içeren başarılı; Aksi takdirde **NULL**.  
  
### <a name="remarks"></a>Açıklamalar  
 Veri depolanır Orta bağlı olarak, dönüş değeri tarafından işaret gerçek türü olabilir `CFile`, `CSharedFile`, veya `COleStreamFile`.  
  
> [!NOTE]
>  `CFile` Bu işlevin dönüş değeri tarafından erişilen nesne çağıran tarafından ait. Çağırana sorumluluğundadır **silmek** `CFile` nesnesi, böylece dosyayı kapatma.  
  
 Daha fazla bilgi için bkz: [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Windows SDK'sındaki.  
  
 Daha fazla bilgi için bkz: [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) Windows SDK'sındaki.  
  
##  <a name="getglobaldata"></a>  COleDataObject::GetGlobalData  
 Bir genel bellek bloğu ayrılamadı ve belirtilen biçime verileri almak için bu işlevi çağırmak bir `HGLOBAL`.  
  
```  
HGLOBAL GetGlobalData(
    CLIPFORMAT cfFormat,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `cfFormat`  
 Veri döndürülecek olan biçimi. Bu parametre bir ön tanımlı Pano biçimleri veya yerel Windows tarafından döndürülen değer olabilir [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) işlevi.  
  
 `lpFormatEtc`  
 İşaret eden bir [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) veri olduğu döndürülecek biçimi açıklayan yapısı. Pano biçimi tarafından belirtilen ötesinde ek biçim bilgilerini belirtmek istiyorsanız, bu parametre için bir değer sağlayın `cfFormat`. Eğer öyleyse **NULL**, diğer alanları için varsayılan değerler kullanılır **FORMATETC** yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa verileri içeren genel bellek bloğu tanıtıcısı; Aksi takdirde **NULL**.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Windows SDK'sındaki.  
  
 Daha fazla bilgi için bkz: [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) Windows SDK'sındaki.  
  
##  <a name="getnextformat"></a>  COleDataObject::GetNextFormat  
 Art arda öğesinden veri almak için kullanılabilir tüm biçimlerini almak için bu işlevini çağırın.  
  
```  
BOOL GetNextFormat(LPFORMATETC lpFormatEtc);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpFormatEtc`  
 İşaret [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) işlev çağrısı döndürüldüğünde, biçimi bilgileri aldığı yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başka bir biçimde olup olmadığını sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrı sonra [COleDataObject::BeginEnumFormats](#beginenumformats), bu veri nesnesi tarafından desteklenen ilk biçimi konumunu depolanır. Art arda çağrılar `GetNextFormat` veri nesnesi kullanılabilir biçimlerde listesini numaralandırır. Kullanılabilir biçimleri listelemek için bu işlevler kullanın.  
  
 Verili bir biçim kullanılabilirliğini denetleyin çağrısı [COleDataObject::IsDataAvailable](#isdataavailable).  
  
 Daha fazla bilgi için bkz: [IEnumXXXX::Next](https://msdn.microsoft.com/library/ms695273.aspx) Windows SDK'sındaki.  
  
##  <a name="isdataavailable"></a>  COleDataObject::IsDataAvailable  
 Belirli bir biçimde OLE öğesinden veri almak için kullanılabilir olup olmadığını belirlemek için bu işlevini çağırın.  
  
```  
BOOL IsDataAvailable(
    CLIPFORMAT cfFormat,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `cfFormat`  
 Tarafından yapısında kullanılması için Pano verileri biçimi işaret için `lpFormatEtc`. Bu parametre bir ön tanımlı Pano biçimleri veya yerel Windows tarafından döndürülen değer olabilir [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) işlevi.  
  
 `lpFormatEtc`  
 İşaret eden bir [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) istenen biçim açıklayan yapısı. Pano biçimi tarafından belirtilen ötesinde ek biçim bilgilerini belirtmek istiyorsanız, bu parametre için bir değer sağlayın `cfFormat`. Eğer öyleyse **NULL**, diğer alanları için varsayılan değerler kullanılır **FORMATETC** yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen biçimde veri varsa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev çağırmadan önce yararlıdır `GetData`, `GetFileData`, veya `GetGlobalData`.  
  
 Daha fazla bilgi için bkz: [IDataObject::QueryGetData](http://msdn.microsoft.com/library/windows/desktop/ms680637) ve [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Windows SDK'sındaki.  
  
 Daha fazla bilgi için bkz: [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) Windows SDK'sındaki.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CRichEditView::QueryAcceptData](../../mfc/reference/cricheditview-class.md#queryacceptdata).  
  
##  <a name="release"></a>  COleDataObject::Release  
 Sahipliğini serbest bırakmak için bu işlevi çağırmak [IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421) önceden ilişkilendirilmiş nesne `COleDataObject` nesne.  
  
```  
void Release();
```  
  
### <a name="remarks"></a>Açıklamalar  
 `IDataObject` İle ilişkili `COleDataObject` çağırarak **Attach** veya `AttachClipboard` açıkça veya framework tarafından. Varsa `bAutoRelease` parametresinin **Attach** olan **FALSE**, `IDataObject` nesnesi değil yayımlanacaktır. Bu durumda, çağıran serbest bırakma için sorumludur `IDataObject` çağırarak [IUnknown::Release](http://msdn.microsoft.com/library/windows/desktop/ms682317).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek HIERSVR](../../visual-cpp-samples.md)   
 [MFC örnek OCLIENT](../../visual-cpp-samples.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [COleDataSource sınıfı](../../mfc/reference/coledatasource-class.md)   
 [COleClientItem sınıfı](../../mfc/reference/coleclientitem-class.md)   
 [COleServerItem Sınıfı](../../mfc/reference/coleserveritem-class.md)
