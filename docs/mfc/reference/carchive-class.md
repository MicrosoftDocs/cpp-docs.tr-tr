---
title: CArchive Sınıfı
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
ms.openlocfilehash: 46d30e38674d10aecdfdbf7be91c48063ba9f493
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377059"
---
# <a name="carchive-class"></a>CArchive Sınıfı

Bu nesneler silindikten sonra devam eden kalıcı ikili formda (genellikle disk depolama) karmaşık bir nesne ağını kaydetmenize olanak tanır.

## <a name="syntax"></a>Sözdizimi

```
class CArchive
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CArchive::CArchive](#carchive)|Bir `CArchive` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CArchive::İptal](#abort)|Bir özel durum atmadan bir arşivkapatır.|
|[CArchive::Kapat](#close)|Yazılmamış verileri temizler ve `CFile`'den keser.|
|[CArchive::Flush](#flush)|Arşiv arabelleğindeki yazılı olmayan verileri temizler.|
|[CArchive::GetFile](#getfile)|Bu `CFile` arşiv için nesne işaretçisini alır.|
|[CArchive::GetObjectSchema](#getobjectschema)|Deserialized `Serialize` nesnenin sürümünü belirlemek için işlevden çağrılır.|
|[CArchive::IsBufferEmpty](#isbufferempty)|Arabellek bir Windows Soketleri alma işlemi sırasında boşaltılan olup olmadığını belirler.|
|[CArchive::IsLoading](#isloading)|Arşivin yüklenip yüklenmediğini belirler.|
|[CArchive::IsStoring](#isstoring)|Arşivin depolanıp depolanmasını belirler.|
|[CArchive::MapObject](#mapobject)|Haritada dosyaya serileştirilen ancak alt nesnelerin başvurulması için kullanılabilen nesneleri yerleştirir.|
|[CArchive::Oku](#read)|Ham bayt okur.|
|[CArchive::ReadClass](#readclass)|Daha önce depolanan bir `WriteClass`sınıf başvurularını okur.|
|[CArchive::ReadObject](#readobject)|Yükleme için nesnenin `Serialize` işlevini çağırır.|
|[CArchive::ReadString](#readstring)|Tek bir metin satırı okur.|
|[CArchive::SerializeClass](#serializeclass)|'nin yönüne bağlı `CArchive` olarak nesnenin sınıf başvurularını okur veya `CArchive`yazar.|
|[CArchive::SetLoadParams](#setloadparams)|Yük dizisinin büyüdüğü boyutu ayarlar. Herhangi bir nesne yüklenmeden `MapObject` veya `ReadObject` önce veya çağrılmadan önce çağrılmalıdır.|
|[CArchive::SetObjectSchema](#setobjectschema)|Arşiv nesnesinde depolanan nesne şemasını ayarlar.|
|[CArchive::SetStoreParams](#setstoreparams)|Karma tablo boyutunu ve serileştirme işlemi sırasında benzersiz nesneleri tanımlamak için kullanılan eşleme boyutunu ayarlar.|
|[CArchive::Yaz](#write)|Ham bayt yazar.|
|[CArchive::WriteClass](#writeclass)|Bir referans `CRuntimeClass` `CArchive`yazar.|
|[CArchive::WriteObject](#writeobject)|Depolamak için `Serialize` nesnenin işlevini çağırır.|
|[CArchive::WriteString](#writestring)|Tek bir metin satırı yazar.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CArchive::operatör&lt;&lt;](#operator_lt_lt)|Nesneleri ve ilkel türleri arşivde depolar.|
|[CArchive::operatör&gt;&gt;](#operator_gt_gt)|Nesneleri ve ilkel türleri arşivden yükler.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CArchive::m_pDocument](#m_pdocument)||

## <a name="remarks"></a>Açıklamalar

`CArchive`taban sınıfa sahip değildir.

Daha sonra nesneleri kalıcı depolamadan yükleyerek bellekte yeniden konumlandırmak. Verileri kalıcı hale getirme işlemine "serileştirme" adı verilir.

Bir arşiv nesnesini bir tür ikili akış olarak düşünebilirsiniz. Giriş/çıktı akışı gibi, arşiv bir dosyayla ilişkilidir ve arabelleğe alınan verilerin depoya ve depolamadan yazılmasına ve okunmasına izin verir. Giriş/çıkış akışı ASCII karakterlerin dizilerini işler, ancak bir arşiv ikili nesne verilerini verimli ve gereksiz olmayan bir biçimde işler.

Bir `CArchive` nesne oluşturamadan önce bir [CFile](../../mfc/reference/cfile-class.md) nesnesi oluşturmanız gerekir. Ayrıca, arşivin yük/depo durumunun dosyanın açık moduyla uyumlu olduğundan emin olmalısınız. Dosya başına bir etkin arşivle sınırlıdır.

Bir `CArchive` nesne oluşturduğunda, onu açık bir `CFile` dosyayı temsil eden bir sınıf nesnesine (veya türetilmiş sınıfa) bağlarsınız. Ayrıca, arşivin yükleme veya depolama için kullanılıp kullanılmayacağını da belirtirsiniz. Bir `CArchive` nesne yalnızca ilkel türleri değil, serileştirme için tasarlanmış [CObject](../../mfc/reference/cobject-class.md)türetilmiş sınıfların nesnelerini de işleyebilir. Serializable sınıf genellikle `Serialize` bir üye işlevi vardır ve genellikle sınıf `CObject`altında açıklandığı gibi [DECLARE_SERIAL](../../mfc/reference/run-time-object-model-services.md#declare_serial) ve [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial) makroları kullanır.

Aşırı yüklenen çıkarma **>>**( ) ve **<<** ekleme ( ) işleçleri, hem ilkel `CObject`türleri hem de türetilmiş sınıfları destekleyen kullanışlı arşiv programlama arabirimleridir.

`CArchive`ayrıca MFC Windows Sockets sınıfları [CSocket](../../mfc/reference/csocket-class.md) ve [CSocketFile](../../mfc/reference/csocketfile-class.md)ile programlamayı destekler. [IsBufferBoş](#isbufferempty) üye işlevi bu kullanımı destekler.

Hakkında daha `CArchive`fazla bilgi için, makaleler [Serialization](../../mfc/serialization-in-mfc.md) ve [Windows Soketleri bakınız: Arşiv ile Soketler kullanma.](../../mfc/windows-sockets-using-sockets-with-archives.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CArchive`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afx.h

## <a name="carchiveabort"></a><a name="abort"></a>CArchive::İptal

Bir özel durum atmadan arşivi kapatmak için bu işlevi arayın.

```
void Abort ();
```

### <a name="remarks"></a>Açıklamalar

`CArchive` Yıkıcı normalde çağırır `Close`, ilişkili `CFile` nesneye kaydedilmemiş tüm verileri temizler. Bu özel durumlara neden olabilir.

Bu özel durumları yakalarken, `Abort` `CArchive` nesneyi yok etmek başka özel durumlara neden olmaz, böylece kullanmak iyi bir fikirdir. Özel durumları işlerken, `CArchive::Abort` [CArchive::Close,,,,,.:Kapat,](#close) `Abort` hataları yok sayar, çünkü hatalar için bir özel durum atmaz.

Nesneyi `CArchive` yığına ayırmak için **yeni** bir şey kullandıysanız, dosyayı kapattıktan sonra silmeniz gerekir.

### <a name="example"></a>Örnek

  CArchive örneğine [bakın:WriteClass](#writeclass).

## <a name="carchivecarchive"></a><a name="carchive"></a>CArchive::CArchive

Bir `CArchive` nesne inşa eder ve nesneleri yüklemek veya depolamak için kullanılıp kullanılmayacağını belirtir.

```
CArchive(
    CFile* pFile,
    UINT nMode,
    int nBufSize = 4096,
    void* lpBuf = NULL);
```

### <a name="parameters"></a>Parametreler

*pFile*<br/>
Kalıcı verilerin `CFile` nihai kaynağı veya hedefi olan nesneye işaretçi.

*nMode*<br/>
Nesnelerin arşivden yüklenip yüklenmeyeceğini veya arşive depolanıp depolanmayacağını belirten bir bayrak. *nMode* parametresi aşağıdaki değerlerden birine sahip olmalıdır:

- `CArchive::load`Arşivden veri yükler. Yalnızca `CFile` okuma izni gerektirir.

- `CArchive::store`Verileri arşive kaydeder. Yazma `CFile` izni gerektirir.

- `CArchive::bNoFlushOnDelete`Arşiv yıkıcı çağrıldığında `Flush` arşivin otomatik olarak aramasını önler. Bu bayrağı ayarlarsanız, yıkıcı çağrılmadan `Close` önce açıkça aramaktan siz sorumlusunuz. Bunu yapmazsanız, verileriniz bozulur.

*nBufSize*<br/>
Dahili dosya arabelleği boyutlarını baytolarak belirten bir arabellek. Varsayılan arabellek boyutunun 4.096 bayt olduğunu unutmayın. Büyük nesneleri düzenli olarak arşivlerseniz, dosya arabellek boyutunun katkatı olan daha büyük bir arabellek boyutu kullanırsanız performansı artırırsınız.

*lpBuf*<br/>
*Boyut nBufSize*kullanıcı tarafından sağlanan arabellek için isteğe bağlı bir işaretçi . Bu parametreyi belirtmezseniz, arşiv yerel yığından bir arabellek ayırır ve nesne yok edildiğinde onu serbest yapar. Arşiv, kullanıcı tarafından sağlanan arabelleği serbest etmez.

### <a name="remarks"></a>Açıklamalar

Arşivi oluşturduktan sonra bu belirtimi değiştiremezsiniz.

Arşivi kapatana kadar dosyanın durumunu değiştirmek için işlemleri kullanamazsınız. `CFile` Böyle bir işlem arşivin bütünlüğüne zarar verir. GetFile üye işlevinden arşivin dosya nesnesini alarak ve [ardından CFile:GetPosition](../../mfc/reference/cfile-class.md#getposition) işlevini kullanarak dosya işaretçisinin konumuna serileştirme sırasında istediğiniz zaman erişebilirsiniz. [GetFile](#getfile) Dosya işaretçisinin konumunu almadan önce [CArchive::Flush'ı](#flush) aramalısınız.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCSerialization#12](../../mfc/codesnippet/cpp/carchive-class_1.cpp)]

## <a name="carchiveclose"></a><a name="close"></a>CArchive::Kapat

Arabellekte kalan tüm verileri temizler, arşivi kapatır ve arşivi dosyadan keser.

```
void Close();
```

### <a name="remarks"></a>Açıklamalar

Arşivüzerinde başka işlem yapılamasına izin verilmemektedir. Bir arşivi kapattıktan sonra, aynı dosya için başka bir arşiv oluşturabilir veya dosyayı kapatabilirsiniz.

Üye işlev, `Close` tüm verilerin arşivden dosyaya aktarılmasını sağlar ve arşivi kullanılamaz hale getirir. Dosyadan depolama ortamına aktarımı tamamlamak için önce [CFile::Close](../../mfc/reference/cfile-class.md#close) ve `CFile` sonra nesneyi yok et kullanmanız gerekir.

### <a name="example"></a>Örnek

  CArchive örneğine [bakın:WriteString](#writestring).

## <a name="carchiveflush"></a><a name="flush"></a>CArchive::Flush

Arşiv arabelleğinde kalan tüm verileri dosyaya yazılmaya zorlar.

```
void Flush();
```

### <a name="remarks"></a>Açıklamalar

Üye işlev, `Flush` tüm verilerin arşivden dosyaya aktarılmasını sağlar. Dosyadan depolama ortamına aktarımı tamamlamak için [CFile::Close'u](../../mfc/reference/cfile-class.md#close) aramanız gerekir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCSerialization#13](../../mfc/codesnippet/cpp/carchive-class_2.cpp)]

## <a name="carchivegetfile"></a><a name="getfile"></a>CArchive::GetFile

Bu `CFile` arşiv için nesne işaretçisini alır.

```
CFile* GetFile() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kullanılan nesneye `CFile` sabit bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Kullanmadan önce arşivi `GetFile`temizlemeniz gerekir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCSerialization#14](../../mfc/codesnippet/cpp/carchive-class_3.cpp)]

## <a name="carchivegetobjectschema"></a><a name="getobjectschema"></a>CArchive::GetObjectSchema

Şu anda `Serialize` seri olarak deserialize edilmekte olan nesnenin sürümünü belirlemek için bu işlevi işlevden çağırın.

```
UINT GetObjectSchema();
```

### <a name="return-value"></a>Dönüş Değeri

Deserialization sırasında, okunan nesnenin sürümü.

### <a name="remarks"></a>Açıklamalar

Bu işlevi çağırmak yalnızca `CArchive` nesne yüklendiğinde geçerlidir [(CArchive::IsLoading](#isloading) sıfırsız döndürür). Bu `Serialize` işlevdeki ilk çağrı olmalı ve yalnızca bir kez çağrılmalıdır. (UINT)-1'in dönüş değeri sürüm numarasının bilinmediğini gösterir.

Türetilen `CObject`bir sınıf, `Serialize` "sürülebilir nesne" yani üye işlevi birden çok sürümü okuyabilen bir nesne oluşturmak için şema sürümünün kendisiyle (IMPLEMENT_SERIAL makroda) birleştirilmiş VERSIONABLE_SCHEMA (bitwise **OR**kullanarak) kullanabilir. Varsayılan çerçeve işlevi (VERSIONABLE_SCHEMA olmadan) sürüm uyumsuz olduğunda bir özel durum atmaktır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCSerialization#15](../../mfc/codesnippet/cpp/carchive-class_4.cpp)]

## <a name="carchiveisbufferempty"></a><a name="isbufferempty"></a>CArchive::IsBufferEmpty

Arşiv nesnesinin iç arabelleği boş olup olmadığını belirlemek için bu üye işlevi arayın.

```
BOOL IsBufferEmpty() const;
```

### <a name="return-value"></a>Dönüş Değeri

Arşivarabellek boşsa sıfır olmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev, MFC Windows Soketleri sınıfı `CSocketFile`ile programlamayı desteklemek için sağlanır. Bir `CFile` nesneyle ilişkili bir arşiv için kullanmanız gerekmez.

Bir `CSocketFile` nesneyle `IsBufferEmpty` ilişkili bir arşivle birlikte kullanmanın nedeni, arşivin arabelleği birden fazla ileti veya kayıt içerebiliyor olmasıdır. Bir ileti aldıktan sonra, `IsBufferEmpty` arabellek boşalana kadar veri almaya devam eden bir döngüyü denetlemek için kullanmalısınız. Daha fazla bilgi için, sınıfın `CAsyncSocket`nasıl kullanılacağını `IsBufferEmpty`gösteren üye işlevini [al'a](../../mfc/reference/casyncsocket-class.md#receive) bakın.

Daha fazla bilgi için [Windows Soketleri: Arşivli Soketleri Kullanma.](../../mfc/windows-sockets-using-sockets-with-archives.md)

## <a name="carchiveisloading"></a><a name="isloading"></a>CArchive::IsLoading

Arşivin veri yükleyip yüklemediğini belirler.

```
BOOL IsLoading() const;
```

### <a name="return-value"></a>Dönüş Değeri

Arşiv şu anda yükleme için kullanılıyorsa sıfırolmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, `Serialize` arşivlenmiş sınıfların işlevleri tarafından çağrılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCSerialization#16](../../mfc/codesnippet/cpp/carchive-class_5.cpp)]

## <a name="carchiveisstoring"></a><a name="isstoring"></a>CArchive::IsStoring

Arşivin veri depolayıp depolamadığını belirler.

```
BOOL IsStoring() const;
```

### <a name="return-value"></a>Dönüş Değeri

Arşiv şu anda depolamak için kullanılıyorsa sıfır olmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, `Serialize` arşivlenmiş sınıfların işlevleri tarafından çağrılır.

Bir `IsStoring` arşivin durumu sıfır değilse, `IsLoading` durumu 0'dır ve tam tersi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCSerialization#17](../../mfc/codesnippet/cpp/carchive-class_6.cpp)]

## <a name="carchivemapobject"></a><a name="mapobject"></a>CArchive::MapObject

Bu üye işlevi, dosyaya gerçekten serileştirilen, ancak alt nesnelerin başvurulması için kullanılabilen nesneleri haritaya yerleştirmek için çağırın.

```
void MapObject(const CObject* pOb);
```

### <a name="parameters"></a>Parametreler

*Pob*<br/>
Depolanan nesneye sabit bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Örneğin, bir belgeyi seri hale ememeyebilirsiniz, ancak belgenin parçası olan öğeleri seri hale getireceksiniz. Arayarak, `MapObject`bu öğelerin veya alt nesnelerin belgeye başvurmasına izin verirsiniz. Ayrıca, serileştirilmiş alt öğeler *m_pDocument* geri işaretçisini seri hale getirebilir.

Nesneye depolayıp yüklediğinizde arayabilirsiniz. `MapObject` `CArchive` `MapObject`belirtilen nesneyi serileştirme ve deserialization `CArchive` sırasında nesne tarafından tutulan iç veri yapılarına ekler, ancak [ReadObject](#readobject) ve [WriteObject'in](#writeobject)aksine, nesne üzerinde serileştirme adını vermez.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCSerialization#18](../../mfc/codesnippet/cpp/carchive-class_7.h)]

[!code-cpp[NVC_MFCSerialization#19](../../mfc/codesnippet/cpp/carchive-class_8.cpp)]

[!code-cpp[NVC_MFCSerialization#20](../../mfc/codesnippet/cpp/carchive-class_9.h)]

[!code-cpp[NVC_MFCSerialization#21](../../mfc/codesnippet/cpp/carchive-class_10.cpp)]

## <a name="carchivem_pdocument"></a><a name="m_pdocument"></a>CArchive::m_pDocument

Varsayılan olarak NULL olarak ayarlanan `CDocument` bu işaretçi, `CArchive` örnek kullanıcısının istediği her şeye ayarlanabilir.

```
CDocument* m_pDocument;
```

### <a name="remarks"></a>Açıklamalar

Bu işaretçinin yaygın kullanımı, seri hale getirilen tüm nesnelere serileştirme işlemi hakkında ek bilgi iletmektir. Bu, işaretçinin serihale edilmekte olan `CDocument`belgeyle (türetilmiş sınıf) başlatılmasıyla, belge içindeki nesnelerin gerekirse belgeye erişebileceği şekilde elde edilir. Bu işaretçi, `COleClientItem` serileştirme sırasında nesneler tarafından da kullanılır.

Çerçeve, bir kullanıcı Dosya Aç veya Kaydet komutu verdiğinde belgenin serihale m_pDocument *ayarlar.* Dosya Aç veya Kaydet dışındaki nedenlerle bir Nesne Bağlama ve Katıştırma (OLE) kapsayıcı belgesini seri hale *m_pDocument.* Örneğin, bir kapsayıcı belgesini Pano'ya seri hale alırken bunu yaparsınız.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCSerialization#35](../../mfc/codesnippet/cpp/carchive-class_11.cpp)]

## <a name="carchiveoperator-ltlt"></a><a name="operator_lt_lt"></a>CArchive::operatör&lt;&lt;

Belirtilen nesneyi veya ilkel türü arşive depolar.

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

Tek `CArchive` bir satırda birden çok ekleme işlecinin olmasını sağlayan bir başvuru.

### <a name="remarks"></a>Açıklamalar

Yukarıdaki son iki sürüm özellikle 64 bit tamsayı depolamak içindir.

Sınıf uygulamanızda IMPLEMENT_SERIAL makrosu kullandıysanız, ekleme işleci korumalı `CObject` `WriteObject`aramalar için aşırı yüklendi. Bu işlev, sırayla, `Serialize` sınıfın işlevini çağırır.

[CStringT](../../atl-mfc-shared/reference/cstringt-class.md) ekleme işleci (<<) tanılama boşaltma ve arşive depolama destekler.

### <a name="example"></a>Örnek

Bu örnek, **int** `CArchive` ve **uzun** türleri ile ekleme işleci << kullanımını göstermektedir.

[!code-cpp[NVC_MFCSerialization#31](../../mfc/codesnippet/cpp/carchive-class_12.cpp)]

### <a name="example"></a>Örnek

Bu örnek 2, `CArchive` `CStringT` ekleme işlecinin << türünü gösterir.

[!code-cpp[NVC_MFCSerialization#32](../../mfc/codesnippet/cpp/carchive-class_13.cpp)]

## <a name="carchiveoperator-gtgt"></a><a name="operator_gt_gt"></a>CArchive::operatör&gt;&gt;

Belirtilen nesneyi veya ilkel türü arşivden yükler.

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

Tek `CArchive` bir satırda birden çok çıkarma işlecisağlayan bir başvuru.

### <a name="remarks"></a>Açıklamalar

Yukarıdaki son iki sürüm özellikle 64 bit tamsayı yüklemek içindir.

Sınıf uygulamanızda IMPLEMENT_SERIAL makroyu kullandıysanız, korumalı `CObject` `ReadObject` işlevi (sıfır çalışma zamanı olmayan sınıf işaretçisi ile) aramak için aşırı yüklenen çıkarma işleçleri. Bu işlev, sırayla, `Serialize` sınıfın işlevini çağırır.

[CStringT](../../atl-mfc-shared/reference/cstringt-class.md) çıkarma işleci (>>) bir arşivden yüklemeyi destekler.

### <a name="example"></a>Örnek

Bu örnek, **int** `CArchive` türüyle >> çıkarma işlecinin kullanımını göstermektedir.

[!code-cpp[NVC_MFCSerialization#33](../../mfc/codesnippet/cpp/carchive-class_14.cpp)]

### <a name="example"></a>Örnek

Bu örnek, ekleme ve `CArchive` çıkarma işleçlerinin \< <ve `CStringT` >> türünü kullanarak kullanımını gösterir.

[!code-cpp[NVC_MFCSerialization#34](../../mfc/codesnippet/cpp/carchive-class_15.cpp)]

## <a name="carchiveread"></a><a name="read"></a>CArchive::Oku

Arşivden belirli sayıda bayt okur.

```
UINT Read(void* lpBuf, UINT nMax);
```

### <a name="parameters"></a>Parametreler

*lpBuf*<br/>
Arşivden okunan verileri almak için kullanıcı tarafından sağlanan arabellek için bir işaretçi.

*nMax*<br/>
Arşivden okunacak bayt sayısını belirten imzasız bir karşıcı.

### <a name="return-value"></a>Dönüş Değeri

Gerçekten okunan bayt sayısını içeren imzasız bir karşıcı. İade değeri istenen sayıdan azsa, dosya sonuna ulaşıldı. Dosya sonu koşulunda özel durum atılmaz.

### <a name="remarks"></a>Açıklamalar

Arşiv baytyorumlamaz.

Nesnelerinizde bulunan `Read` sıradan yapıları `Serialize` okumak için işlevinizdeki üye işlevi kullanabilirsiniz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCSerialization#24](../../mfc/codesnippet/cpp/carchive-class_16.cpp)]

## <a name="carchivereadclass"></a><a name="readclass"></a>CArchive::ReadClass

Daha önce [WriteClass](#writeclass)ile depolanan bir sınıfa başvuru okumak için bu üye işlevi arayın.

```
CRuntimeClass* ReadClass(
    const CRuntimeClass* pClassRefRequested = NULL,
    UINT* pSchema = NULL,
    DWORD* pObTag = NULL);
```

### <a name="parameters"></a>Parametreler

*pClassRefRequested*<br/>
İstenilen sınıf başvurusuna karşılık gelen [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) yapısına bir işaretçi. NULL olabilir.

*pSchema*<br/>
Daha önce depolanan çalışma zamanı sınıfının şemasını işaretçisi.

*pObTag*<br/>
Nesnenin benzersiz etiketine başvuran bir sayı. [ReadObject](#readobject)uygulaması tarafından dahili olarak kullanılır. Yalnızca gelişmiş programlama için açıkta; *pObTag* normalde NULL olmalıdır.

### <a name="return-value"></a>Dönüş Değeri

[CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) yapısıiçin bir işaretçi.

### <a name="remarks"></a>Açıklamalar

*pClassRefRequested* NULL değilse, `ReadClass` arşivlenen sınıf bilgilerinin çalışma zamanı sınıfınızla uyumlu olduğunu doğrular. Uyumlu değilse, `ReadClass` bir [CArchiveException](../../mfc/reference/carchiveexception-class.md)atar.

Çalışma zamanı sınıfınız [DECLARE_SERIAL](../../mfc/reference/run-time-object-model-services.md#declare_serial) ve [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial)kullanmalıdır; aksi `ReadClass` takdirde, bir [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)atacaktır.

*pSchema* NULL ise, depolanan sınıfın şema CArchive çağırarak [alınabilir::GetObjectSchema](#getobjectschema); aksi <strong>\*</strong>takdirde, *pSchema* daha önce depolanan çalışma zamanı sınıfının şema sını içerir.

Sınıf başvurusu hem okuma `ReadClass`hem de yazma işlemlerini yürüten [SerializeClass](#serializeclass) yerine ,'yi kullanabilirsiniz.

### <a name="example"></a>Örnek

  CArchive örneğine [bakın:WriteClass](#writeclass).

## <a name="carchivereadobject"></a><a name="readobject"></a>CArchive::ReadObject

Arşivdeki nesne verilerini okur ve uygun türde bir nesne inşa eder.

```
CObject* ReadObject(const CRuntimeClass* pClass);
```

### <a name="parameters"></a>Parametreler

*pClass*<br/>
Okumayı beklediğiniz nesneye karşılık gelen [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) yapısına işaretçi.

### <a name="return-value"></a>Dönüş Değeri

[CObject::IsKindOf](../../mfc/reference/cobject-class.md#iskindof)kullanarak güvenli bir şekilde doğru türemiş sınıfa atılması gereken bir [CObject](../../mfc/reference/cobject-class.md) işaretçisi.

### <a name="remarks"></a>Açıklamalar

Bu işlev normalde `CArchive` bir **>>** [CObject](../../mfc/reference/cobject-class.md) işaretçisi için aşırı yüklenen çıkarma ( ) işleci tarafından çağrılır. `ReadObject`, sırayla, `Serialize` arşivlenmiş sınıfın işlevini çağırır.

[RUNTIME_CLASS](../../mfc/reference/run-time-object-model-services.md#runtime_class) makrosu tarafından elde edilen sıfır olmayan bir *pClass* parametresi sağlıyorsanız, işlev arşivlenmiş nesnenin çalışma zamanı sınıfını doğrular. Bu, sınıfın uygulanmasında IMPLEMENT_SERIAL makroyu kullandığınızı varsayar.

### <a name="example"></a>Örnek

  CArchive örneğine [bakın:WriteObject](#writeobject).

## <a name="carchivereadstring"></a><a name="readstring"></a>CArchive::ReadString

Metin verilerini `CArchive` nesneyle ilişkili dosyadan arabelleğe okumak için bu üye işlevi arayın.

```
BOOL ReadString(CString& rString);
LPTSTR ReadString(LPTSTR lpsz, UINT nMax);
```

### <a name="parameters"></a>Parametreler

*rString*<br/>
CArchive nesnesi ile ilişkili dosyadan okunduktan sonra ortaya çıkan dize yi içeren bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) başvurusu.

*lpsz*<br/>
Null-sonlandırılan metin dizesini alacak kullanıcı tarafından sağlanan arabellek için bir işaretçi belirtir.

*nMax*<br/>
Okunacak maksimum karakter sayısını belirtir. *Lpsz* tampon boyutundan bir küçük olmalıdır.

### <a name="return-value"></a>Dönüş Değeri

BOOL döndüren sürümünde, başarılı olursa TRUE; YANLIŞ aksi takdirde.

Metin verilerini içeren `LPTSTR`arabelleğe bir işaretçi döndüren sürümde; Dosya sonu ulaşılırsa NULL.

### <a name="remarks"></a>Açıklamalar

*nMax* parametresi ile üye işlevin sürümünde, arabellek *nMax* bir sınıra kadar tutar - 1 karakter. Okuma, bir satır dönüş satırı besleme çifti tarafından durdurulur. Sondaki yeni satır karakterleri her zaman kaldırılır. Her iki durumda da null karakter ('\0') eklenir.

[CArchive::Read](#read) metin modu girişi için de kullanılabilir, ancak bir satır satır besleme çifti üzerinde sona ermez.

### <a name="example"></a>Örnek

  CArchive örneğine [bakın:WriteString](#writestring).

## <a name="carchiveserializeclass"></a><a name="serializeclass"></a>CArchive::SerializeClass

Taban sınıfın sürüm bilgilerini depolamak ve yüklemek istediğinizde bu üye işlevi arayın.

```
void SerializeClass(const CRuntimeClass* pClassRef);
```

### <a name="parameters"></a>Parametreler

*pClassRef*<br/>
Taban sınıf için çalışma zamanı sınıf nesnesine işaretçi.

### <a name="remarks"></a>Açıklamalar

`SerializeClass`'nin yönüne bağlı olarak, `CArchive` nesneye bir sınıfa `CArchive`başvuruyu okur veya yazar. ReadClass ve `SerializeClass` [WriteClass](#readclass) yerine taban sınıf nesneleri serihale getirmek için kullanışlı bir yol olarak kullanın; [WriteClass](#writeclass) `SerializeClass` daha az kod ve daha az parametre gerektirir.

Gibi `ReadClass` `SerializeClass` , arşivlenmiş sınıf bilgilerinin çalışma zamanı sınıfınızla uyumlu olduğunu doğrular. Uyumlu değilse, `SerializeClass` bir [CArchiveException](../../mfc/reference/carchiveexception-class.md)atar.

Çalışma zamanı sınıfınız [DECLARE_SERIAL](../../mfc/reference/run-time-object-model-services.md#declare_serial) ve [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial)kullanmalıdır; aksi `SerializeClass` takdirde, bir [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)atacaktır.

*pRuntimeClass* parametresinin değerini almak için [RUNTIME_CLASS](../../mfc/reference/run-time-object-model-services.md#runtime_class) makroyu kullanın. Taban sınıf [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial) makroyu kullanmış olmalıdır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCSerialization#25](../../mfc/codesnippet/cpp/carchive-class_17.h)]

## <a name="carchivesetloadparams"></a><a name="setloadparams"></a>CArchive::SetLoadParams

Arşivden çok sayıda `SetLoadParams` `CObject`türetilmiş nesneyi okuyacaksanız arayın.

```
void SetLoadParams(UINT nGrowBy = 1024);
```

### <a name="parameters"></a>Parametreler

*nGrowBy*<br/>
Boyut artışı gerekiyorsa ayrılacak en az öğe yuvası sayısı.

### <a name="remarks"></a>Açıklamalar

`CArchive`arşivde depolanan nesnelere yapılan başvuruları gidermek için bir yük dizisi kullanır. `SetLoadParams`yük dizisinin büyüdüğü boyutu ayarlamanızı sağlar.

Herhangi bir `SetLoadParams` nesne yüklendikten sonra veya MapObject veya [ReadObject](#mapobject) çağrıldıktan sonra aramamalısınız. [ReadObject](#readobject)

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCSerialization#26](../../mfc/codesnippet/cpp/carchive-class_18.h)]

## <a name="carchivesetobjectschema"></a><a name="setobjectschema"></a>CArchive::SetObjectSchema

Arşiv nesnesinde depolanan nesne şemasını *nSchema'ya*ayarlamak için bu üye işlevi arayın.

```
void SetObjectSchema(UINT nSchema);
```

### <a name="parameters"></a>Parametreler

*nSchema*<br/>
Nesnenin şeasını belirtir.

### <a name="remarks"></a>Açıklamalar

[GetObjectSchema](#getobjectschema) için bir sonraki çağrı *nSchema*depolanan değeri döndürecek.

Gelişmiş `SetObjectSchema` sürüm için kullanın; örneğin, türemiş bir sınıfın işlevinde okunması `Serialize` için belirli bir sürümü zorlamak istediğinizde.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCSerialization#27](../../mfc/codesnippet/cpp/carchive-class_19.cpp)]

## <a name="carchivesetstoreparams"></a><a name="setstoreparams"></a>CArchive::SetStoreParams

Arşivde çok sayıda `SetStoreParams` `CObject`türetilmiş nesne depolarken kullanın.

```
void SetStoreParams(UINT nHashSize = 2053, UINT nBlockSize = 128);
```

### <a name="parameters"></a>Parametreler

*nHashSize*<br/>
Arabirim işaretçisi eşlemleri için karma tablonun boyutu. Asal sayı olmalı.

*nBlockSize*<br/>
Parametreleri genişletmek için bellek ayırma parçalılığını belirtir. En iyi performans için 2'lik bir güç olmalıdır.

### <a name="remarks"></a>Açıklamalar

`SetStoreParams`karma tablo boyutunu ve serileştirme işlemi sırasında benzersiz nesneleri tanımlamak için kullanılan haritanın blok boyutunu ayarlamanızı sağlar.

Herhangi bir `SetStoreParams` nesne depolandıktan sonra veya [MapObject](#mapobject) veya [WriteObject](#writeobject) çağrıldıktan sonra aramamalısınız.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCSerialization#26](../../mfc/codesnippet/cpp/carchive-class_18.h)]

## <a name="carchivewrite"></a><a name="write"></a>CArchive::Yaz

Arşive belirli sayıda bayt yazar.

```
void Write(const void* lpBuf, INT nMax);
```

### <a name="parameters"></a>Parametreler

*lpBuf*<br/>
Arşive yazılacak verileri içeren kullanıcı tarafından sağlanan arabelleğe işaretçi.

*nMax*<br/>
Arşive yazılacak bayt sayısını belirten bir sonsayı.

### <a name="remarks"></a>Açıklamalar

Arşiv baytbiçimlendirmez.

Nesnelerinizde bulunan `Write` sıradan yapıları `Serialize` yazmak için işlevinizdeki üye işlevi kullanabilirsiniz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCSerialization#23](../../mfc/codesnippet/cpp/carchive-class_20.cpp)]

## <a name="carchivewriteclass"></a><a name="writeclass"></a>CArchive::WriteClass

Türemiş sınıfın serileştirilmesi sırasında bir taban sınıfın sürümünü ve sınıf bilgilerini depolamak için kullanın. `WriteClass`

```
void WriteClass(const CRuntimeClass* pClassRef);
```

### <a name="parameters"></a>Parametreler

*pClassRef*<br/>
İstenilen sınıf başvurusuna karşılık gelen [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) yapısına bir işaretçi.

### <a name="remarks"></a>Açıklamalar

`WriteClass`taban sınıf için [CRuntimeClass'a](../../mfc/reference/cruntimeclass-structure.md) bir `CArchive`başvuru yazar. Başvuruyu almak için [CArchive::ReadClass'ı](#readclass) kullanın.

`WriteClass`arşivlenmiş sınıf bilgilerinin çalışma zamanı sınıfınızla uyumlu olduğunu doğrular. Uyumlu değilse, `WriteClass` bir [CArchiveException](../../mfc/reference/carchiveexception-class.md)atar.

Çalışma zamanı sınıfınız [DECLARE_SERIAL](../../mfc/reference/run-time-object-model-services.md#declare_serial) ve [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial)kullanmalıdır; aksi `WriteClass` takdirde, bir [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)atacaktır.

Sınıf başvurusu hem okuma `WriteClass`hem de yazma işlemlerini yürüten [SerializeClass](#serializeclass) yerine ,'yi kullanabilirsiniz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCSerialization#28](../../mfc/codesnippet/cpp/carchive-class_21.cpp)]

## <a name="carchivewriteobject"></a><a name="writeobject"></a>CArchive::WriteObject

Belirtilenleri `CObject` arşivde saklar.

```
void WriteObject(const CObject* pOb);
```

### <a name="parameters"></a>Parametreler

*Pob*<br/>
Depolanan nesneye sabit bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu fonksiyon normalde `CArchive` ekleme ( **<<**) işleci için `CObject`aşırı yüklenir. `WriteObject`, sırayla, `Serialize` arşivlenmiş sınıfın işlevini çağırır.

Arşivleme sağlamak için IMPLEMENT_SERIAL makroyu kullanmanız gerekir. `WriteObject`arşive ASCII sınıf adını yazar. Bu sınıf adı daha sonra yük işlemi sırasında doğrulanır. Özel bir kodlama düzeni sınıfın birden çok nesnesi için sınıf adının gereksiz çoğaltılmasını önler. Bu şema, birden fazla işaretçi hedefi olan nesnelerin gereksiz depolamasını da engeller.

Tam nesne kodlama yöntemi (ASCII sınıf adının varlığı da dahil olmak üzere) bir uygulama ayrıntısıdır ve kitaplığın gelecekteki sürümlerinde değişebilir.

> [!NOTE]
> Arşivlemeye başlamadan önce tüm nesneleri oluşturmayı, silmeyi ve güncelleştirmeyi bitirin. Arşivleme ile nesne modifikasyonunu karıştırırsanız arşiviniz bozulur.

### <a name="example"></a>Örnek

Sınıfın `CAge`tanımı için CObList örneğine [bakın:CObList.](../../mfc/reference/coblist-class.md#coblist)

[!code-cpp[NVC_MFCSerialization#29](../../mfc/codesnippet/cpp/carchive-class_22.cpp)]

## <a name="carchivewritestring"></a><a name="writestring"></a>CArchive::WriteString

Arabellekten `CArchive` nesneyle ilişkili dosyaya veri yazmak için bu üye işlevi kullanın.

```
void WriteString(LPCTSTR lpsz);
```

### <a name="parameters"></a>Parametreler

*lpsz*<br/>
Null-sonlandırılan metin dizesini içeren bir arabellek için işaretçi belirtir.

### <a name="remarks"></a>Açıklamalar

Sonlandırıcı null karakter ('\0') dosyaya yazılmamıştır; ne de bir newline otomatik olarak yazılır.

`WriteString`disk dolu durum da dahil olmak üzere çeşitli koşullara yanıt olarak bir özel durum atar.

`Write`kullanılabilir, ancak null bir karakter üzerinde sonlandırma yerine, dosyaya istenen bayt sayısını yazar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCSerialization#30](../../mfc/codesnippet/cpp/carchive-class_23.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CFile Sınıfı](../../mfc/reference/cfile-class.md)<br/>
[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[CSocket Sınıfı](../../mfc/reference/csocket-class.md)<br/>
[Csocketfile Sınıfı](../../mfc/reference/csocketfile-class.md)
