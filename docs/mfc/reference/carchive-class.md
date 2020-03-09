---
title: CArchive sınıfı
ms.date: 11/04/2016
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
ms.openlocfilehash: 3cf5c3b7a79e846928b5a7ee0af12a3324e141a3
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78855341"
---
# <a name="carchive-class"></a>CArchive sınıfı

Karmaşık bir nesne ağını, bu nesneler silindikten sonra devam eden kalıcı bir ikili biçimde (genellikle disk depolaması) kaydetmenizi sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CArchive
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CArchive:: CArchive](#carchive)|Bir `CArchive` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CArchive:: Abort](#abort)|Özel durum oluşturmadan bir arşivi kapatır.|
|[CArchive:: Close](#close)|Yazılı olmayan verileri temizler ve `CFile`bağlantısını keser.|
|[CArchive:: Flush](#flush)|Yazdırılamayan verileri arşiv arabelleğinden temizler.|
|[CArchive:: GetFile](#getfile)|Bu arşiv için `CFile` nesne işaretçisini alır.|
|[CArchive:: GetObjectSchema](#getobjectschema)|Seri durumdan çıkarılacak nesnenin sürümünü öğrenmek için `Serialize` işlevinden çağırılır.|
|[CArchive:: IsBufferEmpty](#isbufferempty)|Windows Sockets alma işlemi sırasında arabelleğin boşaltılıp boşaltılmadığını belirler.|
|[CArchive:: ısyükleniyor](#isloading)|Arşivin yüklenip yüklenmediğini belirler.|
|[CArchive:: ısdepo](#isstoring)|Arşivin depolayıp depolanmadığını belirler.|
|[CArchive:: MapObject](#mapobject)|Eşlemeye, dosyaya serileştirilmemiş ancak alt nesnelerin başvurmasına izin veren nesneleri koyar.|
|[CArchive:: Read](#read)|Ham baytları okur.|
|[CArchive:: ReadClass](#readclass)|Daha önce `WriteClass`ile depolanan bir sınıf başvurusunu okur.|
|[CArchive:: ReadObject](#readobject)|Yükleme için bir nesnenin `Serialize` işlevini çağırır.|
|[CArchive:: ReadString](#readstring)|Tek satırlık bir metin okur.|
|[CArchive:: SerializeClass](#serializeclass)|`CArchive`yönüne bağlı olarak `CArchive` nesnesine sınıf başvurusunu okur veya yazar.|
|[CArchive:: SetLoadParams](#setloadparams)|Yükleme dizisinin büyüdüğü boyutu ayarlar. Herhangi bir nesne yüklenmeden önce veya `MapObject` ya da `ReadObject` çağrılmadan önce çağrılmalıdır.|
|[CArchive:: SetObjectSchema](#setobjectschema)|Arşiv nesnesinde depolanan nesne şemasını ayarlar.|
|[CArchive:: SetStoreParams](#setstoreparams)|Serileştirme işlemi sırasında benzersiz nesneleri tanımlamak için kullanılan haritanın karma tablo boyutunu ve blok boyutunu ayarlar.|
|[CArchive:: Write](#write)|Ham baytlar yazar.|
|[CArchive:: WriteClass](#writeclass)|`CArchive``CRuntimeClass` bir başvuru yazar.|
|[CArchive:: WriteObject](#writeobject)|Depolamak için bir nesnenin `Serialize` işlevini çağırır.|
|[CArchive:: WriteString](#writestring)|Tek satırlık bir metin yazar.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CArchive:: operator &lt;&lt;](#operator_lt_lt)|Nesneleri ve temel türleri arşive depolar.|
|[CArchive:: operator &gt;&gt;](#operator_gt_gt)|Arşivden nesneleri ve basit türleri yükler.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CArchive:: m_pDocument](#m_pdocument)||

## <a name="remarks"></a>Açıklamalar

`CArchive` temel bir sınıfa sahip değil.

Daha sonra, nesneleri bellekte reconstituting kalıcı depolamadan yükleyebilirsiniz. Verileri kalıcı hale getirmeye yönelik bu işlem "serileştirme" olarak adlandırılır.

Bir arşiv nesnesini bir tür ikili akış olarak düşünebilirsiniz. Bir giriş/çıkış akışı gibi, bir arşiv bir dosyayla ilişkilendirilir ve verilerin depolama alanına ve depolamaya bağlanmasına izin verir. Bir giriş/çıkış akışı, ASCII karakterlerinin dizilerini işler, ancak bir arşiv ikili nesne verilerini verimli ve gereksiz bir biçimde işler.

`CArchive` nesnesi oluşturabilmeniz için bir [CFile](../../mfc/reference/cfile-class.md) nesnesi oluşturmanız gerekir. Ayrıca, arşivin yük/mağaza durumunun dosyanın açık moduyla uyumlu olduğundan emin olmanız gerekir. Dosya başına bir etkin arşiv ile sınırlı olursunuz.

Bir `CArchive` nesnesi oluşturduğunuzda, bir açık dosyayı temsil eden bir sınıf `CFile` (veya türetilmiş bir sınıf) nesnesine iliştirmiş olursunuz. Ayrıca, arşivin yükleme veya depolama için kullanılıp kullanılmayacağını da belirtirsiniz. `CArchive` nesnesi yalnızca ilkel türler değil, aynı zamanda, serileştirme için tasarlanan [CObject](../../mfc/reference/cobject-class.md)'ten türetilmiş sınıfların nesnelerini de işleyebilir. Seri hale getirilebilir bir sınıf genellikle `Serialize` üye işlevine sahiptir ve genellikle sınıf `CObject`altında açıklandığı gibi [DECLARE_SERIAL](../../mfc/reference/run-time-object-model-services.md#declare_serial) ve [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial) makrolarını kullanır.

Aşırı yüklenmiş ayıklama ( **>>** ) ve ekleme ( **<<** ) işleçleri hem ilkel türleri hem de `CObject`türetilmiş sınıfları destekleyen uygun arşiv programlama arabirimleridir.

`CArchive` Ayrıca MFC Windows Yuvaları sınıfları [CSocket](../../mfc/reference/csocket-class.md) ve [CSocketFile](../../mfc/reference/csocketfile-class.md)ile programlamayı destekler. [IsBufferEmpty](#isbufferempty) üye işlevi bu kullanımı destekler.

`CArchive`hakkında daha fazla bilgi için bkz. [serileştirme](../../mfc/serialization-in-mfc.md) ve [Windows Yuvaları: Arşivlerle yuvalar kullanma](../../mfc/windows-sockets-using-sockets-with-archives.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CArchive`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFX. h

##  <a name="abort"></a>CArchive:: Abort

Özel durum oluşturmadan Arşivi kapatmak için bu işlevi çağırın.

```
void Abort ();
```

### <a name="remarks"></a>Açıklamalar

`CArchive` yıkıcısı normalde, ilişkili `CFile` nesnesine kaydedilmemiş tüm verileri temizlendirilebilen `Close`çağırır. Bu durum özel durumlara neden olabilir.

Bu özel durumları yakalandığınızda, `Abort`kullanmak iyi bir fikirdir. böylece, `CArchive` nesnesinin yeniden kullanılabilmesi daha fazla özel duruma neden olmaz. `CArchive::Abort`, özel durumları işlerken hatalara yönelik bir özel durum oluşturmaz, çünkü [CArchive:: Close](#close), `Abort` hatalara göz ardı eder.

`CArchive` nesnesini yığında ayırmak için **Yeni** kullandıysanız, dosyayı kapattıktan sonra silmeniz gerekir.

### <a name="example"></a>Örnek

  [CArchive:: WriteClass](#writeclass)örneğine bakın.

##  <a name="carchive"></a>CArchive:: CArchive

`CArchive` nesnesi oluşturur ve nesneleri yüklemek veya depolamak için kullanılıp kullanılmayacağını belirtir.

```
CArchive(
    CFile* pFile,
    UINT nMode,
    int nBufSize = 4096,
    void* lpBuf = NULL);
```

### <a name="parameters"></a>Parametreler

*pFile*<br/>
Kalıcı verilerin son kaynağı veya hedefi olan `CFile` nesnesine yönelik bir işaretçi.

*nMode*<br/>
Nesnelerin arşive yüklenip yüklenmeyeceğini veya arşivden depolanmayacağını belirten bayrak. *NMode* parametresi aşağıdaki değerlerden birine sahip olmalıdır:

- `CArchive::load` arşivden veri yükler. Yalnızca `CFile` okuma izni gerektirir.

- `CArchive::store` verileri arşive kaydeder. `CFile` yazma izni gerektirir.

- `CArchive::bNoFlushOnDelete` Arşivi, arşiv yıkıcısı çağrıldığında otomatik olarak `Flush` çağırmasını önler. Bu bayrağı ayarlarsanız, yıkıcı çağrılmadan önce `Close` açıkça çağırmaktan siz sorumlusunuz. Aksi takdirde verileriniz bozulur.

*nBufSize*<br/>
İç dosya arabelleğinin boyutunu bayt cinsinden belirten bir tamsayı. Varsayılan arabellek boyutunun 4.096 bayt olduğunu unutmayın. Büyük nesneleri düzenli olarak arşivliyorsanız, dosya arabelleği boyutunun katı olan daha büyük bir arabellek boyutu kullanırsanız performansı artırabilirsiniz.

*Lparabelleğe*<br/>
Kullanıcı tarafından sağlanan, *nBufSize*boyutundaki arabelleğe yönelik isteğe bağlı bir işaretçi. Bu parametreyi belirtmezseniz, arşiv yerel yığından bir arabellek ayırır ve nesne yok edildiğinde serbest bırakır. Arşiv, Kullanıcı tarafından sağlanan bir arabelleği serbest vermez.

### <a name="remarks"></a>Açıklamalar

Arşivi oluşturduktan sonra bu belirtimi değiştiremezsiniz.

Arşivi kapatana kadar, dosyanın durumunu değiştirmek için `CFile` işlemleri kullanamazsınız. Bu tür bir işlem, arşivin bütünlüğüyle zarar verir. Dosya işaretçisinin konumuna serileştirme sırasında istediğiniz zaman, [GetFile](#getfile) üye işlevinden arşiv dosya nesnesini edinerek ve sonra [CFile:: GetPosition](../../mfc/reference/cfile-class.md#getposition) işlevini kullanarak erişebilirsiniz. Dosya işaretçisinin konumunu almadan önce [CArchive:: Flush](#flush) çağırmalısınız.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCSerialization#12](../../mfc/codesnippet/cpp/carchive-class_1.cpp)]

##  <a name="close"></a>CArchive:: Close

Arabellekte kalan tüm verileri temizler, Arşivi kapatır ve arşiv dosyanın bağlantısını keser.

```
void Close();
```

### <a name="remarks"></a>Açıklamalar

Arşivde başka bir işleme izin verilmiyor. Bir arşivi kapattıktan sonra, aynı dosya için başka bir arşiv oluşturabilir veya dosyayı kapatabilirsiniz.

Üye işlevi `Close` tüm verilerin arşivden dosyaya aktarılmasını sağlar ve arşivi kullanılamaz hale getirir. Dosyadan depolama ortamına aktarımı gerçekleştirmek için önce [CFile:: Close](../../mfc/reference/cfile-class.md#close) kullanmanız ve sonra `CFile` nesnesini yok etmeniz gerekir.

### <a name="example"></a>Örnek

  [CArchive:: WriteString](#writestring)örneğine bakın.

##  <a name="flush"></a>CArchive:: Flush

Arşiv arabelleğinde kalan tüm verileri dosyaya yazılmasına zorlar.

```
void Flush();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi `Flush` tüm verilerin arşivden dosyaya aktarılmasını sağlar. Dosyadan depolama ortamına aktarımı tamamladıktan sonra [CFile:: Close](../../mfc/reference/cfile-class.md#close) çağrısı yapmanız gerekir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCSerialization#13](../../mfc/codesnippet/cpp/carchive-class_2.cpp)]

##  <a name="getfile"></a>CArchive:: GetFile

Bu arşiv için `CFile` nesne işaretçisini alır.

```
CFile* GetFile() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kullanılan `CFile` nesnesine yönelik sabit bir işaretçi.

### <a name="remarks"></a>Açıklamalar

`GetFile`kullanmadan önce Arşivi temizlemeniz gerekir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCSerialization#14](../../mfc/codesnippet/cpp/carchive-class_3.cpp)]

##  <a name="getobjectschema"></a>CArchive:: GetObjectSchema

Şu anda Serisi kaldırılan nesnenin sürümünü öğrenmek için `Serialize` işlevinden bu işlevi çağırın.

```
UINT GetObjectSchema();
```

### <a name="return-value"></a>Dönüş Değeri

Seri durumdan çıkarma sırasında, okunan nesnenin sürümü.

### <a name="remarks"></a>Açıklamalar

Bu işlevi çağırmak yalnızca `CArchive` nesnesi yüklenirken geçerlidir ( [CArchive:: ısyükleme](#isloading) sıfır dışında bir değer döndürür). `Serialize` işlevindeki ilk çağrı olmalıdır ve yalnızca bir kez çağırılır. (UINT)-1 dönüş değeri, sürüm numarasının bilinmediğini gösterir.

`CObject`türetilmiş bir sınıf, şema sürümü kendisi (IMPLEMENT_SERIAL makrosunda) ile birlikte VERSIONABLE_SCHEMA birleştirilmiş (bit düzeyinde **or veya**) kullanarak bir "sürümlenebilir nesne" veya birden çok sürümü okuyabilen bir `Serialize` nesnedir. Varsayılan çerçeve işlevselliği (VERSIONABLE_SCHEMA olmadan), sürüm uyumsuz olduğunda bir özel durum oluşturur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCSerialization#15](../../mfc/codesnippet/cpp/carchive-class_4.cpp)]

##  <a name="isbufferempty"></a>CArchive:: IsBufferEmpty

Arşiv nesnesinin iç arabelleğinin boş olup olmadığını anlamak için bu üye işlevi çağırın.

```
BOOL IsBufferEmpty() const;
```

### <a name="return-value"></a>Dönüş Değeri

Arşiv arabelleği boşsa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev, MFC Windows Yuvaları sınıfı `CSocketFile`programlamayı desteklemek için sağlanır. `CFile` nesnesiyle ilişkili bir arşiv için bunu kullanmanız gerekmez.

`CSocketFile` nesnesiyle ilişkili bir arşiv ile `IsBufferEmpty` kullanmanın nedeni, arşiv arabelleğinin birden fazla ileti veya kayıt içerebileceğinden kaynaklanabilir. Bir ileti aldıktan sonra, arabellek boş olana kadar veri almaya devam eden bir döngüyü denetlemek için `IsBufferEmpty` kullanmanız gerekir. Daha fazla bilgi için, `IsBufferEmpty`nasıl kullanılacağını gösteren `CAsyncSocket`sınıfının [alma](../../mfc/reference/casyncsocket-class.md#receive) üye işlevini inceleyin.

Daha fazla bilgi için bkz. [Windows Yuvaları: Arşivlerle yuvalar kullanma](../../mfc/windows-sockets-using-sockets-with-archives.md).

##  <a name="isloading"></a>CArchive:: ısyükleniyor

Arşivin verileri yükleme olup olmadığını belirler.

```
BOOL IsLoading() const;
```

### <a name="return-value"></a>Dönüş Değeri

Arşiv Şu anda yükleme için kullanılıyorsa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, arşivlenmiş sınıfların `Serialize` işlevleri tarafından çağırılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCSerialization#16](../../mfc/codesnippet/cpp/carchive-class_5.cpp)]

##  <a name="isstoring"></a>CArchive:: ısdepo

Arşivin verileri depolayıp depomadığını belirler.

```
BOOL IsStoring() const;
```

### <a name="return-value"></a>Dönüş Değeri

Arşiv Şu anda depolamada kullanılıyorsa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, arşivlenmiş sınıfların `Serialize` işlevleri tarafından çağırılır.

Bir arşivin `IsStoring` durumu sıfır değilse, `IsLoading` durumu 0 olur ve tam tersi de geçerlidir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCSerialization#17](../../mfc/codesnippet/cpp/carchive-class_6.cpp)]

##  <a name="mapobject"></a>CArchive:: MapObject

Gerçekten dosyaya seri hale getirilmemiş ancak alt nesnelerin başvurmasına izin veren nesneleri haritaya yerleştirmek için bu üye işlevi çağırın.

```
void MapObject(const CObject* pOb);
```

### <a name="parameters"></a>Parametreler

*pOb*<br/>
Depolanmakta olan nesneye yönelik sabit bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Örneğin, bir belgeyi serileştirmeyebilirsiniz, ancak belgenin bir parçası olan öğeleri seri hale getirme. `MapObject`çağırarak, bu öğelerin veya alt nesnelerin belgeye başvurması için izin verin. Ayrıca, serileştirilmiş alt öğeler *m_pDocument* arka işaretçisini seri hale getirilebilir.

`CArchive` nesnesinden ' a depolama ve yükleme yaparken `MapObject` çağırabilirsiniz. `MapObject`, belirtilen nesneyi serileştirme ve seri durumundan çıkarma sırasında `CArchive` nesne tarafından tutulan iç veri yapılarına ekler, ancak [ReadObject](#readobject) ve [WriteObject](#writeobject)'in aksine, nesne üzerinde serileştirme çağırmaz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCSerialization#18](../../mfc/codesnippet/cpp/carchive-class_7.h)]

[!code-cpp[NVC_MFCSerialization#19](../../mfc/codesnippet/cpp/carchive-class_8.cpp)]

[!code-cpp[NVC_MFCSerialization#20](../../mfc/codesnippet/cpp/carchive-class_9.h)]

[!code-cpp[NVC_MFCSerialization#21](../../mfc/codesnippet/cpp/carchive-class_10.cpp)]

##  <a name="m_pdocument"></a>CArchive:: m_pDocument

Varsayılan olarak NULL olarak ayarlanır; bu `CDocument` işaretçisi, `CArchive` örneğinin kullanıcısına istediği her şeye ayarlanabilir.

```
CDocument* m_pDocument;
```

### <a name="remarks"></a>Açıklamalar

Bu işaretçinin ortak kullanımı, serileştirme işlemiyle ilgili ek bilgileri serileştirmekte olan tüm nesnelere iletmenin bir işlemdir. Bu, bir belge (`CDocument`türetilmiş bir sınıf), seri hale getirilmekte olan belgeyle (örneğin, belge içindeki nesneler), gerektiğinde belgeye erişebileceği şekilde başlatılarak elde edilir. Bu işaretçi serileştirme sırasında `COleClientItem` nesneleri tarafından da kullanılır.

Çerçeve, bir Kullanıcı bir dosya aç veya Kaydet komutu sorunlarsa serileştirilen belgeye *m_pDocument* ayarlar. Dosya açma veya kaydetme dışındaki nedenlerle bir nesne bağlama ve Katıştırma (OLE) kapsayıcısı belgesi serileştirmesi yaparsanız, açıkça *m_pDocument*ayarlamanız gerekir. Örneğin, panoya bir kapsayıcı belgesi serileştirilirken bunu yapabilirsiniz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCSerialization#35](../../mfc/codesnippet/cpp/carchive-class_11.cpp)]

##  <a name="operator_lt_lt"></a>CArchive:: operator &lt;&lt;

Belirtilen nesneyi veya basit türü arşive depolar.

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

Tek bir satırda birden çok ekleme işleci sağlayan bir `CArchive` başvurusu.

### <a name="remarks"></a>Açıklamalar

Yukarıdaki son iki sürüm, özellikle 64 bitlik tamsayılar depolamak içindir.

Sınıf uygulamanızda IMPLEMENT_SERIAL makrosunu kullandıysanız, `CObject` için ekleme işleci, korunan `WriteObject`çağırır. Bu işlev sırasıyla sınıfının `Serialize` işlevini çağırır.

[CStringT](../../atl-mfc-shared/reference/cstringt-class.md) ekleme işleci (< <), tanılama dökümünü ve bir arşive depolamayı destekler.

### <a name="example"></a>Örnek

Bu örnek, **int** ve **long** türleriyle < < `CArchive` ekleme işlecinin kullanımını gösterir.

[!code-cpp[NVC_MFCSerialization#31](../../mfc/codesnippet/cpp/carchive-class_12.cpp)]

### <a name="example"></a>Örnek

Bu örnek 2 `CStringT` türü ile < < `CArchive` ekleme işlecinin kullanımını gösterir.

[!code-cpp[NVC_MFCSerialization#32](../../mfc/codesnippet/cpp/carchive-class_13.cpp)]

##  <a name="operator_gt_gt"></a>CArchive:: operator &gt;&gt;

Arşivden belirtilen nesneyi veya basit türü yükler.

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

Tek bir satırda birden çok ayıklama işleci sağlayan bir `CArchive` başvurusu.

### <a name="remarks"></a>Açıklamalar

Yukarıdaki son iki sürüm, özellikle 64 bitlik tamsayılar yüklemek içindir.

Sınıf uygulamanızda IMPLEMENT_SERIAL makrosunu kullandıysanız, `CObject` korumalı `ReadObject` işlevini çağırmak için ayıklama işleçleri aşırı yüklenmiştir (sıfır olmayan çalışma zamanı sınıf işaretçisi ile). Bu işlev sırasıyla sınıfının `Serialize` işlevini çağırır.

[CStringT](../../atl-mfc-shared/reference/cstringt-class.md) ayıklama işleci (> >) bir arşivden yüklemeyi destekler.

### <a name="example"></a>Örnek

Bu örnek, **int** türü ile > > `CArchive` ayıklama işlecinin kullanımını gösterir.

[!code-cpp[NVC_MFCSerialization#33](../../mfc/codesnippet/cpp/carchive-class_14.cpp)]

### <a name="example"></a>Örnek

Bu örnek, > türü ile\< ve > `CStringT` < `CArchive` ekleme ve ayıklama işleçleri kullanımını gösterir.

[!code-cpp[NVC_MFCSerialization#34](../../mfc/codesnippet/cpp/carchive-class_15.cpp)]

##  <a name="read"></a>CArchive:: Read

Arşivden belirtilen sayıda bayt okur.

```
UINT Read(void* lpBuf, UINT nMax);
```

### <a name="parameters"></a>Parametreler

*Lparabelleğe*<br/>
Arşivden okunan verileri almak için Kullanıcı tarafından sağlanan arabelleğin bir işaretçisi.

*Ngünde en çok*<br/>
Arşivden okunacak bayt sayısını belirten işaretsiz bir tamsayı.

### <a name="return-value"></a>Dönüş Değeri

Gerçekten okunan bayt sayısını içeren işaretsiz bir tamsayı. Dönüş değeri istenen sayıdan küçükse dosya sonuna ulaşıldı. Dosya sonu koşulunda hiçbir özel durum oluşturulmaz.

### <a name="remarks"></a>Açıklamalar

Arşiv, baytları yorumlamaz.

Nesnelerinizin içindeki sıradan yapıları okumak için `Serialize` işlevinizdeki `Read` üye işlevini kullanabilirsiniz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCSerialization#24](../../mfc/codesnippet/cpp/carchive-class_16.cpp)]

##  <a name="readclass"></a>CArchive:: ReadClass

Daha önce [WriteClass](#writeclass)ile depolanan bir sınıfa başvuruyu okumak için bu üye işlevini çağırın.

```
CRuntimeClass* ReadClass(
    const CRuntimeClass* pClassRefRequested = NULL,
    UINT* pSchema = NULL,
    DWORD* pObTag = NULL);
```

### <a name="parameters"></a>Parametreler

*pClassRefRequested*<br/>
İstenen sınıf başvurusuna karşılık gelen [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) yapısına yönelik bir işaretçi. NULL olabilir.

*pSchema*<br/>
Daha önce depolanan çalışma zamanı sınıfının şemasına yönelik bir işaretçi.

*pObTag*<br/>
Bir nesnenin benzersiz etiketine başvuran bir sayı. [ReadObject](#readobject)'ın uygulanması tarafından dahili olarak kullanılır. Yalnızca gelişmiş programlama için sunulur; *Pobtag* normalde null olmalıdır.

### <a name="return-value"></a>Dönüş Değeri

[CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) yapısına yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

*PClassRefRequested* null değilse, `ReadClass` arşivlenen sınıf bilgilerinin çalışma zamanı sınıfınız ile uyumlu olduğunu doğrular. Uyumlu değilse `ReadClass` bir [CArchiveException](../../mfc/reference/carchiveexception-class.md)oluşturur.

Çalışma zamanı sınıfınız [DECLARE_SERIAL](../../mfc/reference/run-time-object-model-services.md#declare_serial) ve [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial)kullanmalıdır; Aksi takdirde `ReadClass` bir [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)oluşturur.

*PSchema* null ise, saklı sınıfın şeması [CArchive:: GetObjectSchema](#getobjectschema); çağırarak alınabilir. Aksi halde, <strong>\*</strong> *pSchema* daha önce depolanan çalışma zamanı sınıfının şemasını içerecektir.

Sınıf başvurusunu hem okumayı hem yazmayı işleyen `ReadClass`yerine [SerializeClass](#serializeclass) kullanabilirsiniz.

### <a name="example"></a>Örnek

  [CArchive:: WriteClass](#writeclass)örneğine bakın.

##  <a name="readobject"></a>CArchive:: ReadObject

Arşivden nesne verilerini okur ve uygun türde bir nesne oluşturur.

```
CObject* ReadObject(const CRuntimeClass* pClass);
```

### <a name="parameters"></a>Parametreler

*pClass*<br/>
Okunması beklenen nesneye karşılık gelen [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) yapısına yönelik sabit bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

[CObject:: IsKindOf](../../mfc/reference/cobject-class.md#iskindof)kullanarak doğru türetilmiş sınıfa güvenle dönüştürülmesi gereken [CObject](../../mfc/reference/cobject-class.md) işaretçisi.

### <a name="remarks"></a>Açıklamalar

Bu işlev normalde `CArchive` ayıklama ( **>>** ) işleci tarafından bir [CObject](../../mfc/reference/cobject-class.md) işaretçisi için aşırı yüklenmiş olarak çağrılır. `ReadObject`, sırasıyla arşivlenmiş sınıfın `Serialize` işlevini çağırır.

[RUNTIME_CLASS](../../mfc/reference/run-time-object-model-services.md#runtime_class) makro tarafından elde edilen sıfır olmayan bir *pClass* parametresi sağlarsanız, işlev arşivlenmiş nesnenin çalışma zamanı sınıfını doğrular. Bu, sınıfının uygulamasında IMPLEMENT_SERIAL makrosunu kullanmış olduğunuzu varsayar.

### <a name="example"></a>Örnek

  [CArchive:: WriteObject](#writeobject)örneğine bakın.

##  <a name="readstring"></a>CArchive:: ReadString

`CArchive` nesnesiyle ilişkili dosyadaki bir arabelleğe metin verileri okumak için bu üye işlevi çağırın.

```
BOOL ReadString(CString& rString);
LPTSTR ReadString(LPTSTR lpsz, UINT nMax);
```

### <a name="parameters"></a>Parametreler

*rString*<br/>
CArchive nesnesiyle ilişkili dosyadan okunduktan sonra sonuçtaki dizeyi içeren bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) başvurusu.

*lpsz*<br/>
Null ile sonlandırılmış bir metin dizesi alacak Kullanıcı tarafından sağlanan arabellek için bir işaretçi belirtir.

*Ngünde en çok*<br/>
Okunacak en fazla karakter sayısını belirtir. , *Lpsz* arabelleğinin boyutundan bir daha az olmalıdır.

### <a name="return-value"></a>Dönüş Değeri

BOOL döndüren sürümde, başarılı olursa doğru; Aksi takdirde FALSE.

`LPTSTR`döndüren sürümde, metin verisini içeren arabelleğin bir işaretçisi; Dosya sonu ulaşılırsa NULL.

### <a name="remarks"></a>Açıklamalar

Üye işlevin *NMAX* parametresiyle olan sürümünde, arabellek *NMAX* -1 karakter sınırını tutacaktır. Okuma, bir satır başı satır besleme çifti tarafından durdurulur. Sondaki yeni satır karakterleri her zaman kaldırılır. Her iki durumda da null karakter (' \ 0 ') eklenir.

[CArchive:: Read](#read) , metin modu girişi için de kullanılabilir, ancak bir satır başı satır akış çiftinde sonlanmaz.

### <a name="example"></a>Örnek

  [CArchive:: WriteString](#writestring)örneğine bakın.

##  <a name="serializeclass"></a>CArchive:: SerializeClass

Bir temel sınıfın sürüm bilgilerini depolamak ve yüklemek istediğinizde bu üye işlevini çağırın.

```
void SerializeClass(const CRuntimeClass* pClassRef);
```

### <a name="parameters"></a>Parametreler

*pClassRef*<br/>
Temel sınıf için çalışma zamanı sınıfı nesnesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

`SerializeClass`, `CArchive`yönlerine bağlı olarak `CArchive` nesnesine bir sınıfa olan başvuruyu okur veya yazar. Temel sınıf nesneleri seri hale getirmek için uygun bir yol olarak [ReadClass](#readclass) ve [writeclass](#writeclass) yerine `SerializeClass` kullanın; `SerializeClass` daha az kod ve daha az parametre gerektirir.

`ReadClass`gibi `SerializeClass`, arşivlenmiş sınıf bilgilerinin çalışma zamanı sınıfınız ile uyumlu olduğunu doğrular. Uyumlu değilse `SerializeClass` bir [CArchiveException](../../mfc/reference/carchiveexception-class.md)oluşturur.

Çalışma zamanı sınıfınız [DECLARE_SERIAL](../../mfc/reference/run-time-object-model-services.md#declare_serial) ve [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial)kullanmalıdır; Aksi takdirde `SerializeClass` bir [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)oluşturur.

*PRuntimeClass* parametresinin değerini almak için [RUNTIME_CLASS](../../mfc/reference/run-time-object-model-services.md#runtime_class) makrosunu kullanın. Temel sınıfın [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial) makrosunu kullanmış olması gerekir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCSerialization#25](../../mfc/codesnippet/cpp/carchive-class_17.h)]

##  <a name="setloadparams"></a>CArchive:: SetLoadParams

Bir arşivden çok sayıda `CObject`türetilmiş nesne okuduğunuzda `SetLoadParams` çağırın.

```
void SetLoadParams(UINT nGrowBy = 1024);
```

### <a name="parameters"></a>Parametreler

*nGrowBy*<br/>
Boyut artışı gerekliyse ayrılacak en az öğe yuvası sayısı.

### <a name="remarks"></a>Açıklamalar

`CArchive`, arşivde depolanan nesnelere başvuruları çözümlemek için bir yük dizisi kullanır. `SetLoadParams`, yükleme dizisinin büyüdüğü boyutu ayarlamanıza olanak sağlar.

Herhangi bir nesne yüklendikten sonra veya [MapObject](#mapobject) veya [readobject](#readobject) çağrıldıktan sonra `SetLoadParams` çağrısı yapmanız gerekir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCSerialization#26](../../mfc/codesnippet/cpp/carchive-class_18.h)]

##  <a name="setobjectschema"></a>CArchive:: SetObjectSchema

Arşiv nesnesinde depolanan nesne şemasını *nSchema*'a ayarlamak için bu üye işlevi çağırın.

```
void SetObjectSchema(UINT nSchema);
```

### <a name="parameters"></a>Parametreler

*nSchema*<br/>
Nesnenin şemasını belirtir.

### <a name="remarks"></a>Açıklamalar

[GetObjectSchema](#getobjectschema) 'ya yapılan sonraki çağrı *nSchema*'da depolanan değeri döndürür.

Gelişmiş sürüm oluşturma için `SetObjectSchema` kullanın; Örneğin, belirli bir sürümü türetilmiş bir sınıfın `Serialize` işlevinde okumaya zorlamak istediğinizde.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCSerialization#27](../../mfc/codesnippet/cpp/carchive-class_19.cpp)]

##  <a name="setstoreparams"></a>CArchive:: SetStoreParams

Bir arşivde çok sayıda `CObject`türetilmiş nesne depolarken `SetStoreParams` kullanın.

```
void SetStoreParams(UINT nHashSize = 2053, UINT nBlockSize = 128);
```

### <a name="parameters"></a>Parametreler

*nHashSize*<br/>
Arabirim işaretçisi haritaları için Karma tablosunun boyutu. Bir asal sayı olmalıdır.

*nBlockSize*<br/>
Parametreleri genişletmek için bellek ayırma ayrıntı düzeyini belirtir. En iyi performans için 2 ' nin üssü olmalıdır.

### <a name="remarks"></a>Açıklamalar

`SetStoreParams`, serileştirme işlemi sırasında benzersiz nesneleri tanımlamak için kullanılan haritanın karma tablo boyutunu ve blok boyutunu ayarlamanıza olanak sağlar.

Herhangi bir nesne depolandıktan sonra veya [MapObject](#mapobject) veya [writeobject](#writeobject) çağrıldıktan sonra `SetStoreParams` çağırmamalıdır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCSerialization#26](../../mfc/codesnippet/cpp/carchive-class_18.h)]

##  <a name="write"></a>CArchive:: Write

Arşive belirtilen sayıda bayt yazar.

```
void Write(const void* lpBuf, INT nMax);
```

### <a name="parameters"></a>Parametreler

*Lparabelleğe*<br/>
Arşive yazılacak verileri içeren Kullanıcı tarafından sağlanan arabelleğin bir işaretçisi.

*Ngünde en çok*<br/>
Arşive yazılacak bayt sayısını belirten bir tamsayı.

### <a name="remarks"></a>Açıklamalar

Arşiv, baytları biçimlendirmez.

Nesnelerinizin içinde yer alan sıradan yapıları yazmak için `Serialize` işlevinizdeki `Write` üye işlevini kullanabilirsiniz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCSerialization#23](../../mfc/codesnippet/cpp/carchive-class_20.cpp)]

##  <a name="writeclass"></a>CArchive:: WriteClass

Türetilmiş sınıfın serileştirilmesi sırasında bir temel sınıfın sürümünü ve sınıf bilgilerini depolamak için `WriteClass` kullanın.

```
void WriteClass(const CRuntimeClass* pClassRef);
```

### <a name="parameters"></a>Parametreler

*pClassRef*<br/>
İstenen sınıf başvurusuna karşılık gelen [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) yapısına yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

`WriteClass` temel sınıf için [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) öğesine bir başvuru yazar `CArchive`. Başvuruyu almak için [CArchive:: ReadClass](#readclass) kullanın.

`WriteClass`, arşivlenmiş sınıf bilgilerinin çalışma zamanı sınıfınız ile uyumlu olduğunu doğrular. Uyumlu değilse `WriteClass` bir [CArchiveException](../../mfc/reference/carchiveexception-class.md)oluşturur.

Çalışma zamanı sınıfınız [DECLARE_SERIAL](../../mfc/reference/run-time-object-model-services.md#declare_serial) ve [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial)kullanmalıdır; Aksi takdirde `WriteClass` bir [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)oluşturur.

Sınıf başvurusunu hem okumayı hem yazmayı işleyen `WriteClass`yerine [SerializeClass](#serializeclass) kullanabilirsiniz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCSerialization#28](../../mfc/codesnippet/cpp/carchive-class_21.cpp)]

##  <a name="writeobject"></a>CArchive:: WriteObject

Belirtilen `CObject` arşive depolar.

```
void WriteObject(const CObject* pOb);
```

### <a name="parameters"></a>Parametreler

*pOb*<br/>
Depolanmakta olan nesneye yönelik sabit bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu işlev genellikle `CArchive` ekleme ( **<<** ) işleci tarafından `CObject`için aşırı yüklenmiş olarak çağrılır. `WriteObject`, sırasıyla arşivlenmiş sınıfın `Serialize` işlevini çağırır.

Arşivlemeyi etkinleştirmek için IMPLEMENT_SERIAL makrosunu kullanmanız gerekir. `WriteObject`, ASCII sınıfı adını arşive yazar. Bu sınıf adı, yükleme işlemi sırasında daha sonra onaylanır. Özel bir kodlama şeması, sınıfının birden çok nesnesi için, sınıf adının gereksiz şekilde çoğaltılmasını önler. Bu düzen, birden fazla işaretçiden daha fazla hedef olan nesnelerin yedekli depolanmasını da engeller.

Tam nesne kodlama yöntemi (ASCII sınıf adının varlığı dahil) bir uygulama ayrıntısıdır ve kitaplığın gelecekteki sürümlerinde değişebilir.

> [!NOTE]
>  Arşivleme işlemine başlamadan önce tüm nesnelerinizi oluşturma, silme ve güncelleştirme işlemini tamamlayın. Arşivlemeyi nesne değişikliği ile karıştırırsanız arşiv bozulmuştur.

### <a name="example"></a>Örnek

`CAge`sınıfının bir tanımı için bkz. [CObList:: CObList](../../mfc/reference/coblist-class.md#coblist)için örnek.

[!code-cpp[NVC_MFCSerialization#29](../../mfc/codesnippet/cpp/carchive-class_22.cpp)]

##  <a name="writestring"></a>CArchive:: WriteString

Bir arabellekteki verileri `CArchive` nesnesiyle ilişkili dosyaya yazmak için bu üye işlevini kullanın.

```
void WriteString(LPCTSTR lpsz);
```

### <a name="parameters"></a>Parametreler

*lpsz*<br/>
Null ile sonlandırılmış metin dizesi içeren bir arabelleğin işaretçisini belirtir.

### <a name="remarks"></a>Açıklamalar

Sonlandırıcı null karakteri (' \ 0 ') dosyaya yazılmadı; ya da otomatik olarak yazılmış bir yeni satır.

`WriteString`, disk tam koşulu da dahil olmak üzere çeşitli koşullara yanıt olarak bir özel durum oluşturur.

`Write` da kullanılabilir, ancak null bir karakter üzerinde sonlandırmaktansa, istenen bayt sayısını dosyaya yazar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCSerialization#30](../../mfc/codesnippet/cpp/carchive-class_23.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CFile Sınıfı](../../mfc/reference/cfile-class.md)<br/>
[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[CSocket Sınıfı](../../mfc/reference/csocket-class.md)<br/>
[CSocketFile Sınıfı](../../mfc/reference/csocketfile-class.md)
