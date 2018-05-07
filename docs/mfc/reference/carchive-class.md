---
title: CArchive sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CArchive
- AFX/CArchive
- AFX/CArchive::CArchive
- AFX/CArchive::Abort
- AFX/CArchive::Close
- AFX/CArchive::Flush
- AFX/CArchive::GetFile
- AFX/CArchive::GetObjectSchema
- AFX/CArchive::IsBufferEmpty
- AFX/CArchive::IsLoading
- AFX/CArchive::IsStoring
- AFX/CArchive::MapObject
- AFX/CArchive::Read
- AFX/CArchive::ReadClass
- AFX/CArchive::ReadObject
- AFX/CArchive::ReadString
- AFX/CArchive::SerializeClass
- AFX/CArchive::SetLoadParams
- AFX/CArchive::SetObjectSchema
- AFX/CArchive::SetStoreParams
- AFX/CArchive::Write
- AFX/CArchive::WriteClass
- AFX/CArchive::WriteObject
- AFX/CArchive::WriteString
- AFX/CArchive::m_pDocument
dev_langs:
- C++
helpviewer_keywords:
- CArchive [MFC], CArchive
- CArchive [MFC], Abort
- CArchive [MFC], Close
- CArchive [MFC], Flush
- CArchive [MFC], GetFile
- CArchive [MFC], GetObjectSchema
- CArchive [MFC], IsBufferEmpty
- CArchive [MFC], IsLoading
- CArchive [MFC], IsStoring
- CArchive [MFC], MapObject
- CArchive [MFC], Read
- CArchive [MFC], ReadClass
- CArchive [MFC], ReadObject
- CArchive [MFC], ReadString
- CArchive [MFC], SerializeClass
- CArchive [MFC], SetLoadParams
- CArchive [MFC], SetObjectSchema
- CArchive [MFC], SetStoreParams
- CArchive [MFC], Write
- CArchive [MFC], WriteClass
- CArchive [MFC], WriteObject
- CArchive [MFC], WriteString
- CArchive [MFC], m_pDocument
ms.assetid: 9e950d23-b874-456e-ae4b-fe00781a7699
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f11edef585e699d90d8d33839e0e446cb5a726db
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="carchive-class"></a>CArchive sınıfı
Nesnelerin karmaşık bir ağ nesneleri silindikten sonra devam eden bir kalıcı ikili biçimde (genellikle disk depolama) kaydetmenize olanak sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CArchive  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CArchive::CArchive](#carchive)|Oluşturur bir `CArchive` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CArchive::Abort](#abort)|Bir arşiv bir özel durum oluşturmadan kapatır.|  
|[CArchive::Close](#close)|Unwritten verileri temizler ve bağlantıları keser `CFile`.|  
|[CArchive::Flush](#flush)|Arşiv arabelleğinden unwritten verileri temizler.|  
|[CArchive::GetFile](#getfile)|Alır `CFile` bu arşiv için nesne işaretçisi.|  
|[CArchive::GetObjectSchema](#getobjectschema)|Çağrılır `Serialize` seri durumdan çıkarılmakta olan nesne sürümünü belirlemek için işlev.|  
|[CArchive::IsBufferEmpty](#isbufferempty)|Windows Yuvaları sırasında arabellek boşaltılıp olup olmadığını belirler alma işleminin.|  
|[CArchive::IsLoading](#isloading)|Arşiv yüklenirken olup olmadığını belirler.|  
|[CArchive::IsStoring](#isstoring)|Arşiv depolama olup olmadığını belirler.|  
|[CArchive::MapObject](#mapobject)|Nesneler dosyaya seri değildir, ancak başvurmak alt nesnelerinin için kullanılabilir harita yerleştirir.|  
|[CArchive::Read](#read)|Ham bayt okur.|  
|[CArchive::ReadClass](#readclass)|Sınıf başvurusu daha önce depolanan ile okuma `WriteClass`.|  
|[CArchive::ReadObject](#readobject)|Bir nesnenin çağırır `Serialize` yüklenmesi için işlevi.|  
|[CArchive::ReadString](#readstring)|Tek satırlık metin okur.|  
|[CArchive::SerializeClass](#serializeclass)|Okur veya sınıf başvurusu Yazar `CArchive` nesne yönünü bağlı olarak `CArchive`.|  
|[CArchive::SetLoadParams](#setloadparams)|İçin yük dizi büyür boyutunu belirler. Herhangi bir nesne yüklenmeden önce veya önce çağrılmalıdır `MapObject` veya `ReadObject` olarak adlandırılır.|  
|[CArchive::SetObjectSchema](#setobjectschema)|Arşiv nesnesinde depolanan nesnesi şemasının ayarlar.|  
|[CArchive::SetStoreParams](#setstoreparams)|Karma tablo boyutu ve seri hale getirme işlemi sırasında benzersiz nesneleri tanımlamak için kullanılan eşleme blok boyutunu belirler.|  
|[CArchive::Write](#write)|Ham bayt yazar.|  
|[CArchive::WriteClass](#writeclass)|Bir başvuru Yazar `CRuntimeClass` için `CArchive`.|  
|[CArchive::WriteObject](#writeobject)|Bir nesnenin çağırır `Serialize` depolamak için işlevi.|  
|[CArchive::WriteString](#writestring)|Tek satırlık metin yazar.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CArchive::operator &lt;&lt;](#operator_lt_lt)|Nesneleri ve arşivi ilkel türler depolar.|  
|[CArchive::operator &gt;&gt;](#operator_gt_gt)|Nesneleri ve ilkel türler arşivden yükler.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CArchive::m_pDocument](#m_pdocument)||  
  
## <a name="remarks"></a>Açıklamalar  
 `CArchive` bir taban sınıfı yok.  
  
 Daha sonra bellekte reconstituting kalıcı depolama biriminden nesneleri yükleyebilirsiniz. Bu işlem, veri kalıcı yapma "serileştirme." olarak adlandırılır  
  
 Bir arşiv nesne ikili akışı bir tür olarak düşünebilirsiniz. Bir giriş/çıkış akışı gibi bir arşiv bir dosyayla ilişkili ve arabelleğe alınan yazma ve okuma için ve depolama biriminden verilerin izin verir. Bir giriş/çıkış akışı ASCII karakter dizileri işler, ancak bir arşiv verimli, nonredundant biçimde İkili nesne verilerini işler.  
  
 Oluşturmanız gerekir bir [CFile](../../mfc/reference/cfile-class.md) oluşturabilmeniz için önce nesne bir `CArchive` nesnesi. Ayrıca, arşiv 's yükleme/deposu durum dosyanın açık moduyla uyumlu olduğundan emin olmalısınız. Dosya başına tek etkin arşiv sınırlı olmalıdır.  
  
 Oluşturduğunuzda bir `CArchive` nesnesi, eklediğiniz bu sınıfın bir nesnesi için `CFile` (veya türetilmiş bir sınıf), açık bir dosyayı temsil eder. Ayrıca, Arşiv yüklenirken veya depolamak için kullanılıp kullanılmayacağını belirtin. A `CArchive` yalnızca ilkel türler aynı zamanda nesneleri nesneyi işlenebilecek [CObject](../../mfc/reference/cobject-class.md)-türetilmiş sınıfları seri hale getirme için tasarlanmıştır. Seri hale getirilebilir bir sınıf genellikle sahip bir `Serialize` üye işlevini ve genellikle kullanır [declare_serıal](../../mfc/reference/run-time-object-model-services.md#declare_serial) ve [ımplement_serıal](../../mfc/reference/run-time-object-model-services.md#implement_serial) sınıfı altında açıklandığı gibi makroları `CObject`.  
  
 Aşırı yüklenmiş çıkarma ( **>>**) ve ekleme ( **<<**) işleçler şunlardır: her iki ilkel türlerini destekleyen uygun arşiv programlama arabirimleri ve `CObject` -türetilmiş sınıfları.  
  
 `CArchive` Ayrıca, programlama MFC Windows Sockets sınıflarla destekler [CSocket](../../mfc/reference/csocket-class.md) ve [CSocketFile](../../mfc/reference/csocketfile-class.md). [IsBufferEmpty](#isbufferempty) üye işlevi bu kullanımını destekler.  
  
 Daha fazla bilgi için `CArchive`, makalelerine bakın [seri hale getirme](../../mfc/serialization-in-mfc.md) ve [Windows Yuvaları: arşivlerle kullanılan yuvalara](../../mfc/windows-sockets-using-sockets-with-archives.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `CArchive`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afx.h  
  
##  <a name="abort"></a>  CArchive::Abort  
 Bir özel durum oluşturmadan arşiv kapatmak için bu işlevini çağırın.  
  
```  
void Abort ();
```  
  
### <a name="remarks"></a>Açıklamalar  
 **CArchive** yıkıcı normalde çağıracaktır **Kapat**, hangi kaydedilmedi herhangi bir veri temizleme ilişkili için `CFile` nesnesi. Bu, özel durumlara neden olabilir.  
  
 Bu özel durumları yakalama, bunu kullanmak için iyi bir fikirdir **Abort**, böylece destructing `CArchive` nesnesi değil neden daha fazla özel durum. Özel durumlar, işlerken `CArchive::Abort` bir özel durum hatalarında çünkü oluşturmayacaksa öğesinden farklı olarak [CArchive::Close](#close), **Abort** hatalarını yok sayar.  
  
 Kullandıysanız **yeni** ayırmak için `CArchive` nesne yığında sonra dosya kapattıktan sonra silmeniz gerekir.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CArchive::WriteClass](#writeclass).  
  
##  <a name="carchive"></a>  CArchive::CArchive  
 Oluşturan bir `CArchive` nesne ve onu yüklenirken veya nesneleri depolamak için kullanılıp kullanılmayacağını belirtir.  
  
```  
CArchive(
    CFile* pFile,  
    UINT nMode,  
    int nBufSize = 4096,  
    void* lpBuf = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `pFile`  
 Bir işaretçi `CFile` ultimate kaynak veya hedef kalıcı veri nesnesi.  
  
 `nMode`  
 Nesneleri konumdan yüklendi veya kaldırılacak arşive depolanmış olup olmadığını belirten bir bayrak. `nMode` Parametresi şu değerlerden biri olmalıdır:  
  
- **CArchive::load** arşivden veri yükler. Yalnızca gerektirir `CFile` okuma izni.  
  
- **CArchive::store** arşive verileri kaydeder. Gerektirir `CFile` yazma izni.  
  
- **CArchive::bNoFlushOnDelete** otomatik olarak çağırma arşiv engeller `Flush` arşiv yıkıcı zaman çağrılır. Bu bayrağı ayarlarsanız, açıkça çağırmak için sorumlu **Kapat** yıkıcı çağrılmadan önce. Bunu yapmazsanız, verilerinizi bozuk.  
  
 `nBufSize`  
 İç dosya arabellek boyutunu bayt cinsinden belirten bir tamsayı. Varsayılan arabellek boyutu 4.096 bayt olduğuna dikkat edin. Düzenli olarak büyük nesneler arşivleyin, dosya arabellek boyutu olan daha büyük bir arabellek boyutu kullanırsanız, performansı iyileştirir.  
  
 `lpBuf`  
 Bir kullanıcı tarafından sağlanan arabellek boyutunu isteğe bağlı işaretçisi `nBufSize`. Bu parametre belirtmezseniz, arşiv yerel öbek arabelleğinden ayırır ve nesne bozulduğunda boşaltır. Arşiv bir kullanıcı tarafından sağlanan arabellek boş değil.  
  
### <a name="remarks"></a>Açıklamalar  
 Arşiv oluşturduktan sonra Bu özellikteki değiştiremezsiniz.  
  
 Değil kullanabilir `CFile` arşiv kapatıncaya kadar dosya durumunu değiştirmek için işlemleri. Herhangi bir işlem arşiv bütünlüğünü zarar. Arşiv ait dosya nesnesinden elde ederek seri hale getirme sırasında her zaman dosya işaretçisini konumunu erişebilir [DosyaAl](#getfile) üye işlevini ve sonra kullanarak [CFile::GetPosition](../../mfc/reference/cfile-class.md#getposition) işlevi . Çağırmalısınız [CArchive::Flush](#flush) dosya işaretçisini konumunu alma önce.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCSerialization#12](../../mfc/codesnippet/cpp/carchive-class_1.cpp)]  
  
##  <a name="close"></a>  CArchive::Close  
 Arabellekte kalan verileri temizler, arşiv kapatır ve Arşiv dosyasından bağlantısını keser.  
  
```  
void Close();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Başka bir işlem arşivde izin verilir. Bir arşiv kapattıktan sonra aynı dosya için başka bir arşiv oluşturabilir veya dosyayı kapatın.  
  
 Üye işlevini **Kapat** tüm veriler arşivden dosyasına aktarılır ve, arşiv kullanılamaz hale getirir sağlar. Depolama ortamı dosya aktarımı tamamlamak için önce kullanmanız gerekir [CFile::Close](../../mfc/reference/cfile-class.md#close) ve ardından destroy `CFile` nesnesi.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CArchive::WriteString](#writestring).  
  
##  <a name="flush"></a>  CArchive::Flush  
 Dosyasına yazılacak arşiv arabelleği kalan herhangi bir veri zorlar.  
  
```  
void Flush();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini `Flush` tüm veriler aktarılır, arşivden dosyaya sağlar. Çağırmalısınız [CFile::Close](../../mfc/reference/cfile-class.md#close) dosyasından depolama ortamına aktarımı tamamlamak için.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCSerialization#13](../../mfc/codesnippet/cpp/carchive-class_2.cpp)]  
  
##  <a name="getfile"></a>  CArchive::GetFile  
 Alır `CFile` bu arşiv için nesne işaretçisi.  
  
```  
CFile* GetFile() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sabit bir işaretçi `CFile` kullanılan nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanmadan önce arşiv flush `GetFile`.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCSerialization#14](../../mfc/codesnippet/cpp/carchive-class_3.cpp)]  
  
##  <a name="getobjectschema"></a>  CArchive::GetObjectSchema  
 Bu işlevden çağırma `Serialize` şu anda seri durumdan çıkarılmakta olan nesne sürümünü belirlemek için işlev.  
  
```  
UINT GetObjectSchema();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Seri durumdan çıkarma sırasında okunan nesne sürümü.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev çağırma yalnızca geçerli zaman `CArchive` nesne yükleniyor ( [CArchive::IsLoading](#isloading) sıfır olmayan döndürür). İlk çağrıda olmalıdır `Serialize` işlevi ve adlı yalnızca bir kez. Dönüş değeri ( **UINT**) -1, sürüm numarasını bilinmeyen olduğunu gösterir.  
  
 A `CObject`-türetilmiş sınıf kullanabilir **versıonable_schema** birleştirilmiş (Bitsel kullanarak `OR`) şema sürümü (içinde `IMPLEMENT_SERIAL` makrosu) bir "oluşturulabileceğidir nesnesi," başka bir deyişle, bir nesne, oluşturmakiçin`Serialize` üye işlevi, birden çok sürümü okuyabilir. Varsayılan framework işlevselliği (olmadan **versıonable_schema**) sürümü uyumsuz olduğunda bir özel durum oluşturmaktır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCSerialization#15](../../mfc/codesnippet/cpp/carchive-class_4.cpp)]  
  
##  <a name="isbufferempty"></a>  CArchive::IsBufferEmpty  
 Arşiv nesnenin iç arabellek boş olup olmadığını belirlemek için bu üye işlevini çağırın.  
  
```  
BOOL IsBufferEmpty() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Arşiv 's arabellek boşsa, sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev programlama MFC Windows Sockets sınıfıyla desteklemek için sağlanan `CSocketFile`. İle ilişkili bir arşiv kullanılmak üzere gerekmez bir `CFile` nesnesi.  
  
 Kullanmanın nedeni `IsBufferEmpty` ile ilişkili bir arşiv ile bir `CSocketFile` nesnesidir arşiv 's arabellek birden fazla ileti veya kaydı içerebilir. Bir iletiyi aldıktan sonra kullanmanız gereken `IsBufferEmpty` arabellek boş olmadığı sürece veri alma devam eden bir döngü denetlemek için. Daha fazla bilgi için bkz: [alma](../../mfc/reference/casyncsocket-class.md#receive) sınıfının üye işlevini `CAsyncSocket`, nasıl kullanılacağını gösterir `IsBufferEmpty`.  
  
 Daha fazla bilgi için bkz: [Windows Yuvaları: arşivlerle kullanılan yuvalara](../../mfc/windows-sockets-using-sockets-with-archives.md).  
  
##  <a name="isloading"></a>  CArchive::IsLoading  
 Arşiv verileri yüklenirken olup olmadığını belirler.  
  
```  
BOOL IsLoading() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Arşiv şu anda yükleme için kullanılıyorsa, sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye fonksiyonu tarafından çağrılır `Serialize` arşivlenmiş sınıfların işlevleri.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCSerialization#16](../../mfc/codesnippet/cpp/carchive-class_5.cpp)]  
  
##  <a name="isstoring"></a>  CArchive::IsStoring  
 Arşiv verileri depolama olup olmadığını belirler.  
  
```  
BOOL IsStoring() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Arşiv depolamak için şu anda kullanılıyorsa, sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye fonksiyonu tarafından çağrılır `Serialize` arşivlenmiş sınıfların işlevleri.  
  
 Varsa `IsStoring` bir arşiv durumudur sıfır olmayan, sonra kendi `IsLoading` durumu: 0, bunun tam tersi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCSerialization#17](../../mfc/codesnippet/cpp/carchive-class_6.cpp)]  
  
##  <a name="mapobject"></a>  CArchive::MapObject  
 Nesneleri gerçekten dosyaya seri duruma haritaya yerleştirmek için bu üye işlevini çağırın ancak başvurmak alt nesnelerinin için kullanılabilir.  
  
```  
void MapObject(const CObject* pOb);
```  
  
### <a name="parameters"></a>Parametreler  
 `pOb`  
 Depolanmakta nesne için sabit bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Örneğin, bir belge seri değildir, ancak belgeyi parçası olan öğeleri seri. Çağırarak `MapObject`, bu öğeler veya belgeye başvurmak için alt nesnelerinin, izin verin. Ayrıca, serileştirilmiş alt öğeler serileştirebilen kendi `m_pDocument` geri işaretçi.  
  
 Çağırabilirsiniz `MapObject` zaman depolama ve yüklemek `CArchive` nesnesi. `MapObject` Belirtilen nesne tarafından tutulan iç veri yapılarını ekler `CArchive` nesne seri hale getirme ve seri durumdan çıkarma sırasında ancak aksine [ReadObject](#readobject) ve [WriteObject](#writeobject) **,** arama nesnede seri.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCSerialization#18](../../mfc/codesnippet/cpp/carchive-class_7.h)]  
  
 [!code-cpp[NVC_MFCSerialization#19](../../mfc/codesnippet/cpp/carchive-class_8.cpp)]  
  
 [!code-cpp[NVC_MFCSerialization#20](../../mfc/codesnippet/cpp/carchive-class_9.h)]  
  
 [!code-cpp[NVC_MFCSerialization#21](../../mfc/codesnippet/cpp/carchive-class_10.cpp)]  
  
##  <a name="m_pdocument"></a>  CArchive::m_pDocument  
 Kümesine **NULL** varsayılan olarak, bu işaretçi bir **CDocument** için herhangi bir şey kullanıcısı ayarlanabilir `CArchive` istediği örneği.  
  
```  
CDocument* m_pDocument;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işaretçinin ortak kullanım serileştirilen tüm nesnelere seri hale getirme işlemi hakkında ek bilgi iletmesini sağlamaktır. Bu belgenin işaretçiyle başlatarak elde edilir (bir **CDocument**-türetilmiş sınıf), serileştirilen, belge içindeki nesneleri belge gerekirse erişebilmesini yolu. Bu işaretçinin tarafından da kullanılan `COleClientItem` nesneleri seri hale getirme sırasında.  
  
 Framework kümeleri `m_pDocument` bir kullanıcı bir dosyayı verdiğinde serileştirilen belgeye açın veya Farklı Kaydet komutu. Bir nesne bağlama ve Katıştırma (OLE) kapsayıcı belge dosyayı açma veya kaydetme başka nedenlerle seri, açıkça ayarlamalısınız `m_pDocument`. Örneğin, bir kapsayıcı belge panoya serileştirilirken bunu.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCSerialization#35](../../mfc/codesnippet/cpp/carchive-class_11.cpp)]  
  
##  <a name="operator_lt_lt"></a>  CArchive::operator &lt;&lt;  
 Belirtilen nesne veya ilkel tür arşivi depolar.  
  
```  
friend CArchive& operator<<(
    CArchive& ar,  
    const CObject* pOb);

 
throw(
    CArchiveException*, 
    CFileException*);

 
CArchive& AFXAPI operator<<(
    CArchive& ar,  
    const RECT& rect);

 
CArchive& AFXAPI operator<<(
    CArchive& ar,  
    POINT point);

 
CArchive& AFXAPI operator<<(
    CArchive& ar,  
    SIZE size);

 
template<typename BaseType,  
    class StringTraits> CArchive& operator<<(
    const ATL::CStringT<BaseType,  
    StringTraits>& str);  
  
CArchive& operator<<(BYTE by); 
CArchive& operator<<(WORD w); 
CArchive& operator<<(LONG l); 
CArchive& operator<<(DWORD dw); 
CArchive& operator<<(float f); 
CArchive& operator<<(double d); 
CArchive& operator<<(int i); 
CArchive& operator<<(short w); 
CArchive& operator<<(char ch); 
CArchive& operator<<(wchar_t ch); 
CArchive& operator<<(unsigned u); 
CArchive& operator<<(bool b); 
CArchive& operator<<(ULONGLONG dwdw); 
CArchive& operator<<(LONGLONG dwdw);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `CArchive` tek bir satıra birden çok ekleme işleçlerini etkinleştirir başvuru.  
  
### <a name="remarks"></a>Açıklamalar  
 Son iki yukarıdaki özellikle 64-bit tamsayı depolamak için sürümleridir.  
  
 Kullandıysanız `IMPLEMENT_SERIAL` sınıfı uygulamanız ve ardından için aşırı ekleme işleci makro `CObject` korumalı çağırır **WriteObject**. Bu işlev, buna karşılık, çağıran `Serialize` sınıfının işlevi.  
  
 [CStringT](../../atl-mfc-shared/reference/cstringt-class.md) ekleme işleci (<<) tanılama dökme ve arşive depolama destekler.  
  
### <a name="example"></a>Örnek  
 Bu örnek kullanımını gösteren `CArchive` ekleme işleci << ile `int` ve `long` türleri.  
  
 [!code-cpp[NVC_MFCSerialization#31](../../mfc/codesnippet/cpp/carchive-class_12.cpp)]  
  
### <a name="example"></a>Örnek  
 Bu örnek 2 kullanımını gösteren `CArchive` ekleme işleci << ile `CStringT` türü.  
  
 [!code-cpp[NVC_MFCSerialization#32](../../mfc/codesnippet/cpp/carchive-class_13.cpp)]  
  
##  <a name="operator_gt_gt"></a>  CArchive::operator &gt;&gt;  
 Belirtilen nesne veya ilkel tür arşivden yükler.  
  
```  
friend CArchive& operator>>(
    CArchive& ar,  
    CObject *& pOb);

 
throw(
    CArchiveException*, 
    CFileException*, 
    CMemoryException*);

 
friend CArchive& operator>>(
    CArchive& ar,  
    const CObject *& pOb);

 
throw(
    CArchiveException*, 
    CFileException*, 
    CMemoryException*);

 
CArchive& AFXAPI operator>>(
    CArchive& ar,  
    const RECT& rect);

 
CArchive& AFXAPI operator>>(
    CArchive& ar,  
    POINT point);

 
CArchive& AFXAPI operator>>(
    CArchive& ar,  
    SIZE size);

 
template<typename BaseType,  
    class StringTraits> CArchive& operator>>(
    ATL::CStringT<BaseType, 
    StringTraits>& str);  
  
CArchive& operator>>(BYTE& by);    
CArchive& operator>>(WORD& w);    
CArchive& operator>>(int& i);    
CArchive& operator>>(LONG& l);    
CArchive& operator>>(DWORD& dw);    
CArchive& operator>>(float& f);    
CArchive& operator>>(double& d);    
CArchive& operator>>(short& w);    
CArchive& operator>>(char& ch);    
CArchive& operator>>(wchar_t& ch);    
CArchive& operator>>(unsigned& u);    
CArchive& operator>>(bool& b);    
CArchive& operator>>(ULONGLONG& dwdw);   
CArchive& operator>>(LONGLONG& dwdw);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `CArchive` tek bir satıra birden çok ayıklama işleçlerini etkinleştirir başvuru.  
  
### <a name="remarks"></a>Açıklamalar  
 Son iki yukarıdaki 64-bit tamsayı özellikle yüklenmesini sürümleridir.  
  
 Kullandıysanız `IMPLEMENT_SERIAL` sınıfı uygulamanız ve ardından için aşırı ayıklama işleçlerini makro `CObject` korumalı çağrısı **ReadObject** işlevi (sıfır olmayan çalışma zamanı sınıf işaretçiyle). Bu işlev, buna karşılık, çağıran `Serialize` sınıfının işlevi.  
  
 [CStringT](../../atl-mfc-shared/reference/cstringt-class.md) çıkarma işleci (>>) arşivden yüklenmesini destekliyor.  
  
### <a name="example"></a>Örnek  
 Bu örnek kullanımını gösteren `CArchive` ayıklama işleci >> ile `int` türü.  
  
 [!code-cpp[NVC_MFCSerialization#33](../../mfc/codesnippet/cpp/carchive-class_14.cpp)]  
  
### <a name="example"></a>Örnek  
 Bu örnek kullanımını gösteren `CArchive` ekleme ve çıkarma işleçleri <\< ve >> ile `CStringT` türü.  
  
 [!code-cpp[NVC_MFCSerialization#34](../../mfc/codesnippet/cpp/carchive-class_15.cpp)]  
  
##  <a name="read"></a>  CArchive::Read  
 Belirtilen sayıda baytı arşivden okur.  
  
```  
UINT Read(void* lpBuf, UINT nMax);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpBuf`  
 Veri alma için kullanıcı tarafından sağlanan bir arabellek için bir işaretçi arşivden okuyun.  
  
 `nMax`  
 Arşivden okunacak bayt sayısını belirten imzalanmamış tamsayı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Gerçekte okunan bayt sayısını içeren bir işaretsiz tamsayı. Dönüş değeri İstenen sayıdan daha az ise, dosya sonuna ulaşıldı. Dosya sonu koşula hiçbir özel durum oluşur.  
  
### <a name="remarks"></a>Açıklamalar  
 Arşiv bayt yorumlar değil.  
  
 Kullanabileceğiniz **okuma** üye fonksiyonu içinde `Serialize` işlevi nesneleriniz içinde bulunan sıradan yapıları okumak için.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCSerialization#24](../../mfc/codesnippet/cpp/carchive-class_16.cpp)]  
  
##  <a name="readclass"></a>  CArchive::ReadClass  
 Daha önce depolanan bir sınıf için bir başvuru okumak için bu üye işlev çağrısı [WriteClass](#writeclass).  
  
```  
CRuntimeClass* ReadClass(
    const CRuntimeClass* pClassRefRequested = NULL,  
    UINT* pSchema = NULL,  
    DWORD* pObTag = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `pClassRefRequested`  
 Bir işaretçi [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) istenen sınıf başvurusu karşılık gelen yapısı. Olabilir **NULL**.  
  
 `pSchema`  
 Daha önce depolanan çalışma zamanı sınıfının bir şema için bir işaretçi.  
  
 `pObTag`  
 Bir nesnenin benzersiz etiketine başvuruyor bir sayı. Uygulaması tarafından dahili olarak kullanılan [ReadObject](#readobject). Yalnızca gelişmiş bir programlama kullanıma sunulan; `pObTag` normalde olmalıdır **NULL**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `pClassRefRequested` değil **NULL**, `ReadClass` arşivlenmiş sınıf bilgisi çalışma zamanı sınıfı ile uyumlu olduğunu doğrular. Uyumlu değilse `ReadClass` özel durum oluşturacak bir [CArchiveException](../../mfc/reference/carchiveexception-class.md).  
  
 Çalışma zamanı sınıfınız kullanmalısınız [declare_serıal](../../mfc/reference/run-time-object-model-services.md#declare_serial) ve [ımplement_serıal](../../mfc/reference/run-time-object-model-services.md#implement_serial); Aksi halde, `ReadClass` özel durum oluşturacak bir [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).  
  
 Varsa `pSchema` olan **NULL**, saklı sınıfın şeması çağırarak alınabilir [CArchive::GetObjectSchema](#getobjectschema); Aksi halde, **\*** `pSchema`daha önce depolanan çalışma zamanı sınıfın şeması içerir.  
  
 Kullanabileceğiniz [SerializeClass](#serializeclass) yerine `ReadClass`, hem okuma hem de sınıf başvurusu yazma işler.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CArchive::WriteClass](#writeclass).  
  
##  <a name="readobject"></a>  CArchive::ReadObject  
 Arşivden nesne verilerini okur ve uygun türde bir nesne oluşturur.  
  
```  
CObject* ReadObject(const CRuntimeClass* pClass);
```  
  
### <a name="parameters"></a>Parametreler  
 `pClass`  
 Sabit bir işaretçi [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) beklediğiniz okumak için nesnesine karşılık gelen yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [CObject](../../mfc/reference/cobject-class.md) güvenli bir şekilde doğru dönüştürülmelidir işaretçi türetilmiş sınıf kullanarak [CObject::IsKindOf](../../mfc/reference/cobject-class.md#iskindof).  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev normalde tarafından çağrılır `CArchive` ayıklama ( **>>**) işleci aşırı bir [CObject](../../mfc/reference/cobject-class.md) işaretçi. **ReadObject**, buna karşılık, çağıran `Serialize` arşivlenmiş sınıfının işlevi.  
  
 Sıfır olmayan bir sağlarsanız `pClass` tarafından alınan parametre [RUNTIME_CLASS](../../mfc/reference/run-time-object-model-services.md#runtime_class) makrosu sonra işlevi arşivlenmiş nesnenin çalışma zamanı sınıfı doğrular. Bu kullanmış varsayar `IMPLEMENT_SERIAL` sınıfının uygulamasında makrosu.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CArchive::WriteObject](#writeobject).  
  
##  <a name="readstring"></a>  CArchive::ReadString  
 Bir arabellek ilişkili dosyasından metin veri okunacak bu üye işlevini çağırın `CArchive` nesnesi.  
  
```  
BOOL ReadString(CString& rString); 
LPTSTR ReadString(LPTSTR lpsz, UINT nMax);
```  
  
### <a name="parameters"></a>Parametreler  
 `rString`  
 Bir başvuru bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) CArchive nesneyle ilişkili dosyasından okuduktan sonra sonuç dize içerecek.  
  
 `lpsz`  
 Sonlandırılmış metin dizesini alacak kullanıcı tarafından sağlanan bir arabellek için bir işaretçi belirtir.  
  
 `nMax`  
 Okunacak karakter üst sınırını belirtir. Olmalı boyutundan daha az *lpsz* arabellek.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür sürümünde **BOOL**, **TRUE** başarılıysa; **FALSE** Aksi takdirde.  
  
 Döndürür sürümünde bir `LPTSTR`, metin veri; içeren arabellek için bir işaretçi **NULL** dosya sonu ulaştıysanız.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlev sürümünde `nMax` parametresi, arabellek tutun için bir sınır `nMax` - 1 karakter. Okuma bir satır başı satır besleme çifti tarafından durduruldu. Sondaki yeni satır karakterlerini her zaman kaldırılır. Bir null karakter ('\0'), her iki durumda da eklenir.  
  
 [CArchive::Read](#read) metin modu giriş, ancak değil sonlandırmak için bir satır başı satır besleme çifti üzerinde de kullanılabilir.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CArchive::WriteString](#writestring).  
  
##  <a name="serializeclass"></a>  CArchive::SerializeClass  
 Depolamak ve sürüm bilgileri bir taban sınıfın yüklemek istediğinizde bu üye işlevini çağırın.  
  
```  
void SerializeClass(const CRuntimeClass* pClassRef);
```  
  
### <a name="parameters"></a>Parametreler  
 `pClassRef`  
 Taban sınıfı için bir çalışma zamanı sınıf nesnesi için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 `SerializeClass` okur veya bir sınıfa referansı Yazar `CArchive` yönünü bağlı olarak nesne `CArchive`. Kullanım `SerializeClass` yerine [ReadClass](#readclass) ve [WriteClass](#writeclass) temel sınıf nesneleri; serileştirmek için kolay bir yol olarak `SerializeClass` daha az kod ve daha az parametreleri gerektirir.  
  
 Gibi `ReadClass`, `SerializeClass` arşivlenmiş sınıf bilgisi çalışma zamanı sınıfı ile uyumlu olduğunu doğrular. Uyumlu değilse `SerializeClass` özel durum oluşturacak bir [CArchiveException](../../mfc/reference/carchiveexception-class.md).  
  
 Çalışma zamanı sınıfınız kullanmalısınız [declare_serıal](../../mfc/reference/run-time-object-model-services.md#declare_serial) ve [ımplement_serıal](../../mfc/reference/run-time-object-model-services.md#implement_serial); Aksi halde, `SerializeClass` özel durum oluşturacak bir [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).  
  
 Kullanım [RUNTIME_CLASS](../../mfc/reference/run-time-object-model-services.md#runtime_class) değeri alınacak makrosu `pRuntimeClass` parametresi. Taban sınıf kullanılan [ımplement_serıal](../../mfc/reference/run-time-object-model-services.md#implement_serial) makrosu.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCSerialization#25](../../mfc/codesnippet/cpp/carchive-class_17.h)]  
  
##  <a name="setloadparams"></a>  CArchive::SetLoadParams  
 Çağrı `SetLoadParams` zaman bulacağınızı çok sayıda okumak için `CObject`-arşivden türetilmiş nesneleri.  
  
```  
void SetLoadParams(UINT nGrowBy = 1024);
```  
  
### <a name="parameters"></a>Parametreler  
 `nGrowBy`  
 Öğe yuva boyutu artışı gerekliyse ayırmak için minimum sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 `CArchive` arşivde depolanan nesnelere başvurular çözümlemek için bir yük dizi kullanır. `SetLoadParams` için yük dizi büyür boyutunu ayarlamanızı sağlar.  
  
 Değil çağırmalısınız `SetLoadParams` herhangi bir nesne yüklendikten sonra veya sonra [MapObject](#mapobject) veya [ReadObject](#readobject) olarak adlandırılır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCSerialization#26](../../mfc/codesnippet/cpp/carchive-class_18.h)]  
  
##  <a name="setobjectschema"></a>  CArchive::SetObjectSchema  
 Arşiv nesnesinde depolanan nesnesi şemasının ayarlamak için bu üye işlevini çağırın `nSchema`.  
  
```  
void SetObjectSchema(UINT nSchema);
```  
  
### <a name="parameters"></a>Parametreler  
 `nSchema`  
 Nesnenin şeması belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Sonraki çağrı [GetObjectSchema](#getobjectschema) depolanan değeri döndürür `nSchema`.  
  
 Kullanım `SetObjectSchema` Gelişmiş sürüm oluşturma için; örneğin, istediğinizde de okumak için belirli bir sürüm zorlamak bir `Serialize` işlevi türetilmiş sınıf.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCSerialization#27](../../mfc/codesnippet/cpp/carchive-class_19.cpp)]  
  
##  <a name="setstoreparams"></a>  CArchive::SetStoreParams  
 Kullanım `SetStoreParams` çok sayıda depolarken `CObject`-türetilmiş bir arşiv nesneleri.  
  
```  
void SetStoreParams(UINT nHashSize = 2053, UINT nBlockSize = 128);
```  
  
### <a name="parameters"></a>Parametreler  
 *nHashSize*  
 Arabirim işaretçisi için karma tablo boyutunu eşler. Asal sayı olmalıdır.  
  
 `nBlockSize`  
 Parametreleri genişletmek için bellek ayırma ayrıntı düzeyi belirtir. En iyi performans için 2'in üssü olmalıdır.  
  
### <a name="remarks"></a>Açıklamalar  
 `SetStoreParams` Karma tablo boyutu ve seri hale getirme işlemi sırasında benzersiz nesneleri tanımlamak için kullanılan eşleme blok boyutunu ayarlamanızı sağlar.  
  
 Değil çağırmalısınız `SetStoreParams` herhangi bir nesne depolandıktan sonra veya sonra [MapObject](#mapobject) veya [WriteObject](#writeobject) olarak adlandırılır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCSerialization#26](../../mfc/codesnippet/cpp/carchive-class_18.h)]  
  
##  <a name="write"></a>  CArchive::Write  
 Belirtilen sayıda baytı arşive yazar.  
  
```  
void Write(const void* lpBuf, INT nMax);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpBuf`  
 Arşive yazılacak veriler içeren bir kullanıcı tarafından sağlanan arabellek için bir işaretçi.  
  
 `nMax`  
 Arşive yazılacak bayt sayısını belirten bir tamsayı.  
  
### <a name="remarks"></a>Açıklamalar  
 Arşiv bayt biçiminde değil.  
  
 Kullanabileceğiniz **yazma** üye fonksiyonu içinde `Serialize` sıradan yapıları yazmak için işlevi nesneleriniz içinde yer alır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCSerialization#23](../../mfc/codesnippet/cpp/carchive-class_20.cpp)]  
  
##  <a name="writeclass"></a>  CArchive::WriteClass  
 Kullanım `WriteClass` türetilmiş sınıf serileştirme sırasında bir taban sınıfın sürüm ve sınıf bilgilerini depolamak için.  
  
```  
void WriteClass(const CRuntimeClass* pClassRef);
```  
  
### <a name="parameters"></a>Parametreler  
 `pClassRef`  
 Bir işaretçi [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) istenen sınıf başvurusu karşılık gelen yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
 `WriteClass` bir başvuru Yazar [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) taban sınıfı için `CArchive`. Kullanım [CArchive::ReadClass](#readclass) başvuru alınamadı.  
  
 `WriteClass` Arşivlenen sınıf bilgisi çalışma zamanı sınıfı ile uyumlu olduğunu doğrular. Uyumlu değilse `WriteClass` özel durum oluşturacak bir [CArchiveException](../../mfc/reference/carchiveexception-class.md).  
  
 Çalışma zamanı sınıfınız kullanmalısınız [declare_serıal](../../mfc/reference/run-time-object-model-services.md#declare_serial) ve [ımplement_serıal](../../mfc/reference/run-time-object-model-services.md#implement_serial); Aksi halde, `WriteClass` özel durum oluşturacak bir [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).  
  
 Kullanabileceğiniz [SerializeClass](#serializeclass) yerine `WriteClass`, hem okuma hem de sınıf başvurusu yazma işler.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCSerialization#28](../../mfc/codesnippet/cpp/carchive-class_21.cpp)]  
  
##  <a name="writeobject"></a>  CArchive::WriteObject  
 Belirtilen depolar `CObject` arşivi.  
  
```  
void WriteObject(const CObject* pOb);
```  
  
### <a name="parameters"></a>Parametreler  
 `pOb`  
 Depolanmakta nesne için sabit bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev normalde tarafından çağrılır `CArchive` ekleme ( **<<**) işleci aşırı `CObject`. **WriteObject**, buna karşılık, çağıran `Serialize` arşivlenmiş sınıfının işlevi.  
  
 Kullanmalısınız `IMPLEMENT_SERIAL` arşivleme etkinleştirmek için makrosu. **WriteObject** ASCII sınıf adı arşive yazar. Bu sınıf adı daha sonra yükleme işlemi sırasında doğrulanır. Özel bir kodlama düzeni sınıfın birden çok nesne için sınıf adı gereksiz yinelenmesini engeller. Bu düzen, aynı zamanda birden fazla işaretçinin hedeflerine nesnelerin yedekli depolama engeller.  
  
 Kodlama yöntemi (ASCII sınıf adı varlığını dahil) tam nesnesi bir uygulama ayrıntılarını ve gelecekte kitaplık sürümleri değiştirebilirsiniz.  
  
> [!NOTE]
>  Oluşturma, silme ve tüm nesneler arşivleyin başlamadan önce güncelleştirme tamamlayın. Nesne değişikliği arşivleme karışımı varsa, arşiv bozuk.  
  
### <a name="example"></a>Örnek  
 Sınıf tanımının için `CAge`, örneğin bkz [CObList::CObList](../../mfc/reference/coblist-class.md#coblist).  
  
 [!code-cpp[NVC_MFCSerialization#29](../../mfc/codesnippet/cpp/carchive-class_22.cpp)]  
  
##  <a name="writestring"></a>  CArchive::WriteString  
 Verileri bir arabelleğinden ile ilişkili dosya yazmak için bu üye işlevi kullanın `CArchive` nesnesi.  
  
```  
void WriteString(LPCTSTR lpsz);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpsz`  
 Sonlandırılmış metin dizesini içeren bir arabellek için bir işaretçi belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Sonlandırma null karakteri ('\0') dosyasına yazılmaz; veya bir satır başı karakteri otomatik olarak yazılır.  
  
 `WriteString` disk dolu koşulu dahil olmak üzere çeşitli koşullar yanıtta bir özel durum oluşturur.  
  
 **Yazma** , de kullanılabilir, ancak bir null karakter sonlandırma yerine, istenen bayt sayısı dosyasına yazar.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCSerialization#30](../../mfc/codesnippet/cpp/carchive-class_23.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CFile sınıfı](../../mfc/reference/cfile-class.md)   
 [CObject sınıfı](../../mfc/reference/cobject-class.md)   
 [CSocket sınıfı](../../mfc/reference/csocket-class.md)   
 [CSocketFile Sınıfı](../../mfc/reference/csocketfile-class.md)
