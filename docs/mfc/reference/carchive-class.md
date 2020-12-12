---
description: 'Daha fazla bilgi edinin: CArchive sınıfı'
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
ms.openlocfilehash: bcae8d18503c5ef4acce965f720b947bb1c706ac
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97118764"
---
# <a name="carchive-class"></a>CArchive sınıfı

Karmaşık bir nesne ağını, bu nesneler silindikten sonra devam eden kalıcı bir ikili biçimde (genellikle disk depolaması) kaydetmenizi sağlar.

## <a name="syntax"></a>Syntax

```
class CArchive
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CArchive:: CArchive](#carchive)|Bir `CArchive` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CArchive:: Abort](#abort)|Özel durum oluşturmadan bir arşivi kapatır.|
|[CArchive:: Close](#close)|Yazılı olmayan verileri temizler ve bağlantısını keser `CFile` .|
|[CArchive:: Flush](#flush)|Yazdırılamayan verileri arşiv arabelleğinden temizler.|
|[CArchive:: GetFile](#getfile)|`CFile`Bu arşiv için nesne işaretçisini alır.|
|[CArchive:: GetObjectSchema](#getobjectschema)|`Serialize`Seri durumdan çıkarılacak nesnenin sürümünü öğrenmek için işlevinden çağırılır.|
|[CArchive:: IsBufferEmpty](#isbufferempty)|Windows Sockets alma işlemi sırasında arabelleğin boşaltılıp boşaltılmadığını belirler.|
|[CArchive:: ısyükleniyor](#isloading)|Arşivin yüklenip yüklenmediğini belirler.|
|[CArchive:: ısdepo](#isstoring)|Arşivin depolayıp depolanmadığını belirler.|
|[CArchive:: MapObject](#mapobject)|Eşlemeye, dosyaya serileştirilmemiş ancak alt nesnelerin başvurmasına izin veren nesneleri koyar.|
|[CArchive:: Read](#read)|Ham baytları okur.|
|[CArchive:: ReadClass](#readclass)|Daha önce ile depolanan bir sınıf başvurusunu okur `WriteClass` .|
|[CArchive:: ReadObject](#readobject)|Yükleme için bir nesnenin `Serialize` işlevini çağırır.|
|[CArchive:: ReadString](#readstring)|Tek satırlık bir metin okur.|
|[CArchive:: SerializeClass](#serializeclass)|`CArchive`Öğesinin yönüne bağlı olarak nesnesine sınıf başvurusunu okur veya yazar `CArchive` .|
|[CArchive:: SetLoadParams](#setloadparams)|Yükleme dizisinin büyüdüğü boyutu ayarlar. Herhangi bir nesne yüklenmeden veya çağrılmadan önce çağrılmalıdır `MapObject` `ReadObject` .|
|[CArchive:: SetObjectSchema](#setobjectschema)|Arşiv nesnesinde depolanan nesne şemasını ayarlar.|
|[CArchive:: SetStoreParams](#setstoreparams)|Serileştirme işlemi sırasında benzersiz nesneleri tanımlamak için kullanılan haritanın karma tablo boyutunu ve blok boyutunu ayarlar.|
|[CArchive:: Write](#write)|Ham baytlar yazar.|
|[CArchive:: WriteClass](#writeclass)|Öğesine bir başvuru yazar `CRuntimeClass` `CArchive` .|
|[CArchive:: WriteObject](#writeobject)|Depolamak için bir nesnenin `Serialize` işlevini çağırır.|
|[CArchive:: WriteString](#writestring)|Tek satırlık bir metin yazar.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CArchive:: işleci &lt;&lt;](#operator_lt_lt)|Nesneleri ve temel türleri arşive depolar.|
|[CArchive:: işleci &gt;&gt;](#operator_gt_gt)|Arşivden nesneleri ve basit türleri yükler.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CArchive:: m_pDocument](#m_pdocument)||

## <a name="remarks"></a>Açıklamalar

`CArchive` taban sınıfına sahip değildir.

Daha sonra, nesneleri bellekte reconstituting kalıcı depolamadan yükleyebilirsiniz. Verileri kalıcı hale getirmeye yönelik bu işlem "serileştirme" olarak adlandırılır.

Bir arşiv nesnesini bir tür ikili akış olarak düşünebilirsiniz. Bir giriş/çıkış akışı gibi, bir arşiv bir dosyayla ilişkilendirilir ve verilerin depolama alanına ve depolamaya bağlanmasına izin verir. Bir giriş/çıkış akışı, ASCII karakterlerinin dizilerini işler, ancak bir arşiv ikili nesne verilerini verimli ve gereksiz bir biçimde işler.

Bir nesne oluşturabilmeniz için önce bir [CFile](../../mfc/reference/cfile-class.md) nesnesi oluşturmanız gerekir `CArchive` . Ayrıca, arşivin yük/mağaza durumunun dosyanın açık moduyla uyumlu olduğundan emin olmanız gerekir. Dosya başına bir etkin arşiv ile sınırlı olursunuz.

Bir `CArchive` nesne oluşturduğunuzda, onu `CFile` açık bir dosyayı temsil eden sınıfının bir nesnesine (veya türetilmiş bir sınıfa) iliştirmiş olursunuz. Ayrıca, arşivin yükleme veya depolama için kullanılıp kullanılmayacağını da belirtirsiniz. Bir `CArchive` nesne yalnızca ilkel türler değil, aynı zamanda, serileştirme için tasarlanan [CObject](../../mfc/reference/cobject-class.md)'ten türetilmiş sınıfların nesnelerini de işleyebilir. Seri hale getirilebilir bir sınıf genellikle `Serialize` üye işlevine sahiptir ve genellikle [DECLARE_SERIAL](../../mfc/reference/run-time-object-model-services.md#declare_serial) ve [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial) makrolarını kullanır `CObject` .

Aşırı yüklenmiş ayıklama ( **>>** ) ve ekleme ( **<<** ) işleçleri, hem basit türler hem de türetilmiş sınıfları destekleyen kullanışlı arşiv programlama arayüzleridir `CObject` .

`CArchive` MFC Windows Yuvaları sınıfları [CSocket](../../mfc/reference/csocket-class.md) ve [CSocketFile](../../mfc/reference/csocketfile-class.md)ile programlamayı da destekler. [IsBufferEmpty](#isbufferempty) üye işlevi bu kullanımı destekler.

Hakkında daha fazla bilgi için `CArchive` bkz. [serileştirme](../../mfc/serialization-in-mfc.md) ve [Windows Yuvaları: Arşivlerle yuvalar kullanma](../../mfc/windows-sockets-using-sockets-with-archives.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CArchive`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFX. h

## <a name="carchiveabort"></a><a name="abort"></a> CArchive:: Abort

Özel durum oluşturmadan Arşivi kapatmak için bu işlevi çağırın.

```cpp
void Abort ();
```

### <a name="remarks"></a>Açıklamalar

`CArchive`Yok edicisi normalde `Close` , ilişkili nesnesine kaydedilmemiş tüm verileri temizedecek şekilde çağırır `CFile` . Bu durum özel durumlara neden olabilir.

Bu özel durumları yakalandığınızda, `Abort` daha iyi özel durumlara neden olmayacak şekilde, kullanmak iyi bir fikirdir `CArchive` . Özel durumları işlerken `CArchive::Abort` hatalara yönelik bir özel durum oluşturmaz, çünkü [CArchive:: Close](#close), `Abort` hatalardan yokar.

**`new`** Nesneyi yığında ayırmak için kullandıysanız `CArchive` , dosyayı kapattıktan sonra silmeniz gerekir.

### <a name="example"></a>Örnek

  [CArchive:: WriteClass](#writeclass)örneğine bakın.

## <a name="carchivecarchive"></a><a name="carchive"></a> CArchive:: CArchive

Bir `CArchive` nesne oluşturur ve nesneleri yüklemek ya da depolamak için kullanılıp kullanılmayacağını belirtir.

```
CArchive(
    CFile* pFile,
    UINT nMode,
    int nBufSize = 4096,
    void* lpBuf = NULL);
```

### <a name="parameters"></a>Parametreler

*pFile*<br/>
`CFile`Kalıcı verilerin son kaynağı veya hedefi olan nesneye yönelik bir işaretçi.

*nMode*<br/>
Nesnelerin arşive yüklenip yüklenmeyeceğini veya arşivden depolanmayacağını belirten bayrak. *NMode* parametresi aşağıdaki değerlerden birine sahip olmalıdır:

- `CArchive::load` Arşivden veri yükler. Yalnızca `CFile` okuma izni gerektirir.

- `CArchive::store` Verileri arşive kaydeder. `CFile`Yazma izni gerektirir.

- `CArchive::bNoFlushOnDelete` Arşiv yıkıcısı çağrıldığında arşivin otomatik olarak çağrılmasını önler `Flush` . Bu bayrağı ayarlarsanız, yıkıcı çağrılmadan önce açıkça çağrılmadan sorumlu olursunuz `Close` . Aksi takdirde verileriniz bozulur.

*nBufSize*<br/>
İç dosya arabelleğinin boyutunu bayt cinsinden belirten bir tamsayı. Varsayılan arabellek boyutunun 4.096 bayt olduğunu unutmayın. Büyük nesneleri düzenli olarak arşivliyorsanız, dosya arabelleği boyutunun katı olan daha büyük bir arabellek boyutu kullanırsanız performansı artırabilirsiniz.

*Lparabelleğe*<br/>
Kullanıcı tarafından sağlanan, *nBufSize* boyutundaki arabelleğe yönelik isteğe bağlı bir işaretçi. Bu parametreyi belirtmezseniz, arşiv yerel yığından bir arabellek ayırır ve nesne yok edildiğinde serbest bırakır. Arşiv, Kullanıcı tarafından sağlanan bir arabelleği serbest vermez.

### <a name="remarks"></a>Açıklamalar

Arşivi oluşturduktan sonra bu belirtimi değiştiremezsiniz.

`CFile`Arşivi kapatana kadar, dosya durumunu değiştirmek için işlemleri kullanamazsınız. Bu tür bir işlem, arşivin bütünlüğüyle zarar verir. Dosya işaretçisinin konumuna serileştirme sırasında istediğiniz zaman, [GetFile](#getfile) üye işlevinden arşiv dosya nesnesini edinerek ve sonra [CFile:: GetPosition](../../mfc/reference/cfile-class.md#getposition) işlevini kullanarak erişebilirsiniz. Dosya işaretçisinin konumunu almadan önce [CArchive:: Flush](#flush) çağırmalısınız.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCSerialization#12](../../mfc/codesnippet/cpp/carchive-class_1.cpp)]

## <a name="carchiveclose"></a><a name="close"></a> CArchive:: Close

Arabellekte kalan tüm verileri temizler, Arşivi kapatır ve arşiv dosyanın bağlantısını keser.

```cpp
void Close();
```

### <a name="remarks"></a>Açıklamalar

Arşivde başka bir işleme izin verilmiyor. Bir arşivi kapattıktan sonra, aynı dosya için başka bir arşiv oluşturabilir veya dosyayı kapatabilirsiniz.

Üye işlevi, `Close` tüm verilerin arşivden dosyaya aktarılmasını sağlar ve arşivi kullanılamaz hale getirir. Dosyadan depolama ortamına aktarımı gerçekleştirmek için önce [CFile:: Close](../../mfc/reference/cfile-class.md#close) kullanmanız ve sonra nesneyi yok etmeniz gerekir `CFile` .

### <a name="example"></a>Örnek

  [CArchive:: WriteString](#writestring)örneğine bakın.

## <a name="carchiveflush"></a><a name="flush"></a> CArchive:: Flush

Arşiv arabelleğinde kalan tüm verileri dosyaya yazılmasına zorlar.

```cpp
void Flush();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, `Flush` tüm verilerin arşivden dosyaya aktarılmasını sağlar. Dosyadan depolama ortamına aktarımı tamamladıktan sonra [CFile:: Close](../../mfc/reference/cfile-class.md#close) çağrısı yapmanız gerekir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCSerialization#13](../../mfc/codesnippet/cpp/carchive-class_2.cpp)]

## <a name="carchivegetfile"></a><a name="getfile"></a> CArchive:: GetFile

`CFile`Bu arşiv için nesne işaretçisini alır.

```
CFile* GetFile() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kullanılan nesneye yönelik sabit bir işaretçi `CFile` .

### <a name="remarks"></a>Açıklamalar

' İ kullanmadan önce Arşivi temizlemeniz gerekir `GetFile` .

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCSerialization#14](../../mfc/codesnippet/cpp/carchive-class_3.cpp)]

## <a name="carchivegetobjectschema"></a><a name="getobjectschema"></a> CArchive:: GetObjectSchema

`Serialize`Şu anda Serisi kaldırılan nesnenin sürümünü öğrenmek için bu işlevi işlevinden çağırın.

```
UINT GetObjectSchema();
```

### <a name="return-value"></a>Dönüş Değeri

Seri durumdan çıkarma sırasında, okunan nesnenin sürümü.

### <a name="remarks"></a>Açıklamalar

Bu işlevi çağırmak yalnızca `CArchive` nesne yüklenirken geçerlidir ( [CArchive:: ısyükleme](#isloading) sıfır dışında). Bu, işlevdeki ilk çağrı olmalıdır `Serialize` ve yalnızca bir kez çağırılır. (UINT)-1 dönüş değeri, sürüm numarasının bilinmediğini gösterir.

`CObject`Türetilmiş bir sınıf, bir "sürümlenebilir nesne", yani `Serialize` üye işlevi birden çok sürümü okuyabilen bir nesne oluşturmak için şema IMPLEMENT_SERIAL sürümü ile birlikte VERSIONABLE_SCHEMA birleştirilmiş (bit düzeyinde OR kullanarak) kullanabilir. Varsayılan çerçeve işlevselliği (VERSIONABLE_SCHEMA olmadan), sürüm uyumsuz olduğunda bir özel durum oluşturur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCSerialization#15](../../mfc/codesnippet/cpp/carchive-class_4.cpp)]

## <a name="carchiveisbufferempty"></a><a name="isbufferempty"></a> CArchive:: IsBufferEmpty

Arşiv nesnesinin iç arabelleğinin boş olup olmadığını anlamak için bu üye işlevi çağırın.

```
BOOL IsBufferEmpty() const;
```

### <a name="return-value"></a>Dönüş Değeri

Arşiv arabelleği boşsa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev, MFC Windows Yuvaları sınıfı ile programlamayı desteklemek için sağlanır `CSocketFile` . Bir nesneyle ilişkili bir arşiv için kullanmanız gerekmez `CFile` .

`IsBufferEmpty`Bir nesneyle ilişkili bir arşiv ile kullanılması nedeni, `CSocketFile` Arşiv arabelleğinin birden fazla ileti veya kayıt içerebileceğinden kaynaklanabilir. Bir ileti aldıktan sonra, `IsBufferEmpty` arabellek boş olana kadar veri almaya devam eden bir döngüyü denetlemek için öğesini kullanmanız gerekir. Daha fazla bilgi için bkz. sınıfının [alma](../../mfc/reference/casyncsocket-class.md#receive) üye işlevi `CAsyncSocket` , öğesinin nasıl kullanılacağını gösterir `IsBufferEmpty` .

Daha fazla bilgi için bkz. [Windows Yuvaları: Arşivlerle yuvalar kullanma](../../mfc/windows-sockets-using-sockets-with-archives.md).

## <a name="carchiveisloading"></a><a name="isloading"></a> CArchive:: ısyükleniyor

Arşivin verileri yükleme olup olmadığını belirler.

```
BOOL IsLoading() const;
```

### <a name="return-value"></a>Dönüş Değeri

Arşiv Şu anda yükleme için kullanılıyorsa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, `Serialize` arşivlenmiş sınıfların işlevleri tarafından çağırılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCSerialization#16](../../mfc/codesnippet/cpp/carchive-class_5.cpp)]

## <a name="carchiveisstoring"></a><a name="isstoring"></a> CArchive:: ısdepo

Arşivin verileri depolayıp depomadığını belirler.

```
BOOL IsStoring() const;
```

### <a name="return-value"></a>Dönüş Değeri

Arşiv Şu anda depolamada kullanılıyorsa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, `Serialize` arşivlenmiş sınıfların işlevleri tarafından çağırılır.

`IsStoring`Bir arşivin durumu sıfır değilse, `IsLoading` durumu 0 olur ve tam tersi de geçerlidir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCSerialization#17](../../mfc/codesnippet/cpp/carchive-class_6.cpp)]

## <a name="carchivemapobject"></a><a name="mapobject"></a> CArchive:: MapObject

Gerçekten dosyaya seri hale getirilmemiş ancak alt nesnelerin başvurmasına izin veren nesneleri haritaya yerleştirmek için bu üye işlevi çağırın.

```cpp
void MapObject(const CObject* pOb);
```

### <a name="parameters"></a>Parametreler

*pOb*<br/>
Depolanmakta olan nesneye yönelik sabit bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Örneğin, bir belgeyi serileştirmeyebilirsiniz, ancak belgenin bir parçası olan öğeleri seri hale getirme. Çağırarak `MapObject` , bu öğelerin veya alt nesnelerin belgeye başvurması için izin verin. Ayrıca, serileştirilmiş alt öğeler *m_pDocument* arka işaretçisini seri hale getirilebilir.

`MapObject`Nesnesine ne zaman depolanacağını ve nesnesinden yükleme yapabilirsiniz `CArchive` . `MapObject` belirtilen nesneyi `CArchive` serileştirme ve seri durumundan çıkarma sırasında nesne tarafından tutulan iç veri yapılarına ekler, ancak [ReadObject](#readobject) ve [WriteObject](#writeobject)'in aksine, nesne üzerinde serileştirme çağırmaz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCSerialization#18](../../mfc/codesnippet/cpp/carchive-class_7.h)]

[!code-cpp[NVC_MFCSerialization#19](../../mfc/codesnippet/cpp/carchive-class_8.cpp)]

[!code-cpp[NVC_MFCSerialization#20](../../mfc/codesnippet/cpp/carchive-class_9.h)]

[!code-cpp[NVC_MFCSerialization#21](../../mfc/codesnippet/cpp/carchive-class_10.cpp)]

## <a name="carchivem_pdocument"></a><a name="m_pdocument"></a> CArchive:: m_pDocument

Varsayılan olarak NULL olarak ayarlanır; Bu işaretçi, `CDocument` örnek kullanıcısının istediği her şeye ayarlanabilir `CArchive` .

```
CDocument* m_pDocument;
```

### <a name="remarks"></a>Açıklamalar

Bu işaretçinin ortak kullanımı, serileştirme işlemiyle ilgili ek bilgileri serileştirmekte olan tüm nesnelere iletmenin bir işlemdir. Bu, işaretçi, `CDocument` seri hale getirilen belgeyle (bir türetilmiş sınıf), gerekirse belge içindeki nesnelerin belgeye erişebileceği bir şekilde başlatılarak elde edilir. Bu işaretçi, `COleClientItem` serileştirme sırasında nesneler tarafından da kullanılır.

Çerçeve, bir Kullanıcı bir dosya aç veya Kaydet komutu sorunlarsa serileştirilen belgeye *m_pDocument* ayarlar. Dosya açma veya kaydetme dışındaki nedenlerle bir nesne bağlama ve Katıştırma (OLE) kapsayıcısı belgesi serileştirmesi yaparsanız, açıkça *m_pDocument* ayarlamanız gerekir. Örneğin, panoya bir kapsayıcı belgesi serileştirilirken bunu yapabilirsiniz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCSerialization#35](../../mfc/codesnippet/cpp/carchive-class_11.cpp)]

## <a name="carchiveoperator-ltlt"></a><a name="operator_lt_lt"></a> CArchive:: işleci &lt;&lt;

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

`CArchive`Tek bir satırda birden çok ekleme işleci sağlayan bir başvuru.

### <a name="remarks"></a>Açıklamalar

Yukarıdaki son iki sürüm, özellikle 64 bitlik tamsayılar depolamak içindir.

Sınıf uygulamanızda IMPLEMENT_SERIAL makrosunu kullandıysanız, korumalı çağrılar için ekleme işleci aşırı yüklenmiştir `CObject` `WriteObject` . Bu işlev, sırasıyla `Serialize` sınıfının işlevini çağırır.

[CStringT](../../atl-mfc-shared/reference/cstringt-class.md) ekleme işleci (<<), tanılama dökümünü ve bir arşive depolamayı destekler.

### <a name="example"></a>Örnek

Bu örnek, `CArchive` ve türleriyle birlikte << ekleme işlecinin kullanımını gösterir **`int`** **`long`** .

[!code-cpp[NVC_MFCSerialization#31](../../mfc/codesnippet/cpp/carchive-class_12.cpp)]

### <a name="example"></a>Örnek

Bu örnek 2, `CArchive` tür ile << ekleme işlecinin kullanımını gösterir `CStringT` .

[!code-cpp[NVC_MFCSerialization#32](../../mfc/codesnippet/cpp/carchive-class_13.cpp)]

## <a name="carchiveoperator-gtgt"></a><a name="operator_gt_gt"></a> CArchive:: işleci &gt;&gt;

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

`CArchive`Tek bir satırda birden çok ayıklama işleci sağlayan bir başvuru.

### <a name="remarks"></a>Açıklamalar

Yukarıdaki son iki sürüm, özellikle 64 bitlik tamsayılar yüklemek içindir.

Sınıf uygulamanızda IMPLEMENT_SERIAL makrosunu kullandıysanız, korumalı işlevi çağırmak için ayıklama işleçleri aşırı yüklenmiştir `CObject` `ReadObject` (sıfır dışında çalışma zamanı sınıf işaretçisi ile). Bu işlev, sırasıyla `Serialize` sınıfının işlevini çağırır.

[CStringT](../../atl-mfc-shared/reference/cstringt-class.md) ayıklama işleci (>>) bir arşivden yüklemeyi destekler.

### <a name="example"></a>Örnek

Bu örnek, `CArchive` türü ile >> ayıklama işlecinin kullanımını gösterir **`int`** .

[!code-cpp[NVC_MFCSerialization#33](../../mfc/codesnippet/cpp/carchive-class_14.cpp)]

### <a name="example"></a>Örnek

Bu örnek, `CArchive` <> ekleme ve ayıklama işleçleri kullanımını gösterir \< and > `CStringT` .

[!code-cpp[NVC_MFCSerialization#34](../../mfc/codesnippet/cpp/carchive-class_15.cpp)]

## <a name="carchiveread"></a><a name="read"></a> CArchive:: Read

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

`Read` `Serialize` Nesnelerinizin içinde bulunan sıradan yapıları okumak için işlevinizdeki üye işlevini kullanabilirsiniz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCSerialization#24](../../mfc/codesnippet/cpp/carchive-class_16.cpp)]

## <a name="carchivereadclass"></a><a name="readclass"></a> CArchive:: ReadClass

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

*PClassRefRequested* null değilse, `ReadClass` arşivlenen sınıf bilgilerinin çalışma zamanı sınıfınız ile uyumlu olduğunu doğrular. Uyumlu değilse, `ReadClass` bir [CArchiveException](../../mfc/reference/carchiveexception-class.md)oluşturur.

Çalışma zamanı sınıfınız [DECLARE_SERIAL](../../mfc/reference/run-time-object-model-services.md#declare_serial) ve [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial)kullanmalıdır; Aksi takdirde, `ReadClass` bir [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)oluşturur.

*PSchema* null ise, saklı sınıfın şeması [CArchive:: GetObjectSchema](#getobjectschema); çağırarak alınabilir. Aksi halde, <strong>\*</strong> *pSchema* daha önce depolanan çalışma zamanı sınıfının şemasını içerecektir.

Sınıf başvurusunun hem okuma hem de yazmayı işleyen yerine [SerializeClass](#serializeclass) `ReadClass` öğesini kullanabilirsiniz.

### <a name="example"></a>Örnek

  [CArchive:: WriteClass](#writeclass)örneğine bakın.

## <a name="carchivereadobject"></a><a name="readobject"></a> CArchive:: ReadObject

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

Bu işlev, `CArchive` **>>** bir [CObject](../../mfc/reference/cobject-class.md) işaretçisi için normalde ayıklama () işleci tarafından çağrılır. `ReadObject`, sırasıyla `Serialize` arşivlenen sınıfın işlevini çağırır.

[RUNTIME_CLASS](../../mfc/reference/run-time-object-model-services.md#runtime_class) makro tarafından elde edilen sıfır olmayan bir *pClass* parametresi sağlarsanız, işlev arşivlenmiş nesnenin çalışma zamanı sınıfını doğrular. Bu, sınıfının uygulamasında IMPLEMENT_SERIAL makrosunu kullanmış olduğunuzu varsayar.

### <a name="example"></a>Örnek

  [CArchive:: WriteObject](#writeobject)örneğine bakın.

## <a name="carchivereadstring"></a><a name="readstring"></a> CArchive:: ReadString

Nesne ile ilişkili dosyadaki bir arabelleğe metin verisi okumak için bu üye işlevi çağırın `CArchive` .

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

Döndüren sürümünde `LPTSTR` , metin verisini içeren arabelleğin bir işaretçisi; Dosya sonu ulaşılırsa NULL.

### <a name="remarks"></a>Açıklamalar

Üye işlevin *NMAX* parametresiyle olan sürümünde, arabellek *NMAX* -1 karakter sınırını tutacaktır. Okuma, bir satır başı satır besleme çifti tarafından durdurulur. Sondaki yeni satır karakterleri her zaman kaldırılır. Her iki durumda da null karakter (' \ 0 ') eklenir.

[CArchive:: Read](#read) , metin modu girişi için de kullanılabilir, ancak bir satır başı satır akış çiftinde sonlanmaz.

### <a name="example"></a>Örnek

  [CArchive:: WriteString](#writestring)örneğine bakın.

## <a name="carchiveserializeclass"></a><a name="serializeclass"></a> CArchive:: SerializeClass

Bir temel sınıfın sürüm bilgilerini depolamak ve yüklemek istediğinizde bu üye işlevini çağırın.

```cpp
void SerializeClass(const CRuntimeClass* pClassRef);
```

### <a name="parameters"></a>Parametreler

*pClassRef*<br/>
Temel sınıf için çalışma zamanı sınıfı nesnesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

`SerializeClass` bir sınıfa başvuruyu okur veya `CArchive` yönüne bağlı olarak nesnesine yazar `CArchive` . `SerializeClass` [ReadClass](#readclass) ve [WriteClass](#writeclass) ' ın yerine, temel sınıf nesneleri seri hale getirmek için uygun bir yol olarak kullanın; `SerializeClass` daha az kod ve daha az parametre gerektirir.

Benzer şekilde `ReadClass` , `SerializeClass` arşivlenmiş sınıf bilgilerinin çalışma zamanı sınıfınız ile uyumlu olduğunu doğrular. Uyumlu değilse, `SerializeClass` bir [CArchiveException](../../mfc/reference/carchiveexception-class.md)oluşturur.

Çalışma zamanı sınıfınız [DECLARE_SERIAL](../../mfc/reference/run-time-object-model-services.md#declare_serial) ve [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial)kullanmalıdır; Aksi takdirde, `SerializeClass` bir [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)oluşturur.

*PRuntimeClass* parametresinin değerini almak için [RUNTIME_CLASS](../../mfc/reference/run-time-object-model-services.md#runtime_class) makrosunu kullanın. Temel sınıfın [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial) makrosunu kullanmış olması gerekir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCSerialization#25](../../mfc/codesnippet/cpp/carchive-class_17.h)]

## <a name="carchivesetloadparams"></a><a name="setloadparams"></a> CArchive:: SetLoadParams

`SetLoadParams` `CObject` Bir arşivden çok sayıda türetilmiş nesneyi okuyacaksanız çağırın.

```cpp
void SetLoadParams(UINT nGrowBy = 1024);
```

### <a name="parameters"></a>Parametreler

*nGrowBy*<br/>
Boyut artışı gerekliyse ayrılacak en az öğe yuvası sayısı.

### <a name="remarks"></a>Açıklamalar

`CArchive` Arşivde depolanan nesnelere başvuruları çözümlemek için bir Load dizisi kullanır. `SetLoadParams` Yükleme dizisinin büyüdüğü boyutu ayarlamanıza olanak sağlar.

`SetLoadParams`Herhangi bir nesne yüklendikten sonra veya [MapObject](#mapobject) veya [ReadObject](#readobject) çağrıldıktan sonra çağrı yapmanız gerekir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCSerialization#26](../../mfc/codesnippet/cpp/carchive-class_18.h)]

## <a name="carchivesetobjectschema"></a><a name="setobjectschema"></a> CArchive:: SetObjectSchema

Arşiv nesnesinde depolanan nesne şemasını *nSchema*'a ayarlamak için bu üye işlevi çağırın.

```cpp
void SetObjectSchema(UINT nSchema);
```

### <a name="parameters"></a>Parametreler

*nSchema*<br/>
Nesnenin şemasını belirtir.

### <a name="remarks"></a>Açıklamalar

[GetObjectSchema](#getobjectschema) 'ya yapılan sonraki çağrı *nSchema*'da depolanan değeri döndürür.

`SetObjectSchema`Gelişmiş sürüm oluşturma için kullanın; örneğin, belirli bir sürümü türetilmiş bir sınıfın işlevinde okumaya zorlamak istediğinizde `Serialize` .

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCSerialization#27](../../mfc/codesnippet/cpp/carchive-class_19.cpp)]

## <a name="carchivesetstoreparams"></a><a name="setstoreparams"></a> CArchive:: SetStoreParams

`SetStoreParams` `CObject` Bir arşivde çok sayıda türetilmiş nesne depolarken kullanın.

```cpp
void SetStoreParams(UINT nHashSize = 2053, UINT nBlockSize = 128);
```

### <a name="parameters"></a>Parametreler

*nHashSize*<br/>
Arabirim işaretçisi haritaları için Karma tablosunun boyutu. Bir asal sayı olmalıdır.

*nBlockSize*<br/>
Parametreleri genişletmek için bellek ayırma ayrıntı düzeyini belirtir. En iyi performans için 2 ' nin üssü olmalıdır.

### <a name="remarks"></a>Açıklamalar

`SetStoreParams` serileştirme işlemi sırasında benzersiz nesneleri tanımlamak için kullanılan haritanın karma tablo boyutunu ve blok boyutunu ayarlamanıza olanak sağlar.

`SetStoreParams`Herhangi bir nesne depolandıktan sonra veya [MapObject](#mapobject) veya [WriteObject](#writeobject) çağrıldıktan sonra çağrı yapmanız gerekir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCSerialization#26](../../mfc/codesnippet/cpp/carchive-class_18.h)]

## <a name="carchivewrite"></a><a name="write"></a> CArchive:: Write

Arşive belirtilen sayıda bayt yazar.

```cpp
void Write(const void* lpBuf, INT nMax);
```

### <a name="parameters"></a>Parametreler

*Lparabelleğe*<br/>
Arşive yazılacak verileri içeren Kullanıcı tarafından sağlanan arabelleğin bir işaretçisi.

*Ngünde en çok*<br/>
Arşive yazılacak bayt sayısını belirten bir tamsayı.

### <a name="remarks"></a>Açıklamalar

Arşiv, baytları biçimlendirmez.

`Write` `Serialize` Nesnelerinizin içinde yer alan sıradan yapıları yazmak için işlevinizdeki üye işlevini kullanabilirsiniz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCSerialization#23](../../mfc/codesnippet/cpp/carchive-class_20.cpp)]

## <a name="carchivewriteclass"></a><a name="writeclass"></a> CArchive:: WriteClass

`WriteClass`Türetilmiş sınıfın serileştirilmesi sırasında bir temel sınıfın sürümünü ve sınıf bilgilerini depolamak için kullanın.

```cpp
void WriteClass(const CRuntimeClass* pClassRef);
```

### <a name="parameters"></a>Parametreler

*pClassRef*<br/>
İstenen sınıf başvurusuna karşılık gelen [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) yapısına yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

`WriteClass` taban sınıfına ait [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) öğesine bir başvuru yazar `CArchive` . Başvuruyu almak için [CArchive:: ReadClass](#readclass) kullanın.

`WriteClass` arşivlenmiş sınıf bilgilerinin çalışma zamanı sınıfınız ile uyumlu olduğunu doğrular. Uyumlu değilse, `WriteClass` bir [CArchiveException](../../mfc/reference/carchiveexception-class.md)oluşturur.

Çalışma zamanı sınıfınız [DECLARE_SERIAL](../../mfc/reference/run-time-object-model-services.md#declare_serial) ve [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial)kullanmalıdır; Aksi takdirde, `WriteClass` bir [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)oluşturur.

Sınıf başvurusunun hem okuma hem de yazmayı işleyen yerine [SerializeClass](#serializeclass) `WriteClass` öğesini kullanabilirsiniz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCSerialization#28](../../mfc/codesnippet/cpp/carchive-class_21.cpp)]

## <a name="carchivewriteobject"></a><a name="writeobject"></a> CArchive:: WriteObject

Belirtilen arşivi depolar `CObject` .

```cpp
void WriteObject(const CObject* pOb);
```

### <a name="parameters"></a>Parametreler

*pOb*<br/>
Depolanmakta olan nesneye yönelik sabit bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu işlev normalde, `CArchive` için ekleme ( **<<** ) işleci tarafından çağrılır `CObject` . `WriteObject`, sırasıyla `Serialize` arşivlenen sınıfın işlevini çağırır.

Arşivlemeyi etkinleştirmek için IMPLEMENT_SERIAL makrosunu kullanmanız gerekir. `WriteObject` ASCII sınıf adını arşive yazar. Bu sınıf adı, yükleme işlemi sırasında daha sonra onaylanır. Özel bir kodlama şeması, sınıfının birden çok nesnesi için, sınıf adının gereksiz şekilde çoğaltılmasını önler. Bu düzen, birden fazla işaretçiden daha fazla hedef olan nesnelerin yedekli depolanmasını da engeller.

Tam nesne kodlama yöntemi (ASCII sınıf adının varlığı dahil) bir uygulama ayrıntısıdır ve kitaplığın gelecekteki sürümlerinde değişebilir.

> [!NOTE]
> Arşivleme işlemine başlamadan önce tüm nesnelerinizi oluşturma, silme ve güncelleştirme işlemini tamamlayın. Arşivlemeyi nesne değişikliği ile karıştırırsanız arşiv bozulmuştur.

### <a name="example"></a>Örnek

Sınıfının tanımı için `CAge` bkz. [CObList:: CObList](../../mfc/reference/coblist-class.md#coblist)için örnek.

[!code-cpp[NVC_MFCSerialization#29](../../mfc/codesnippet/cpp/carchive-class_22.cpp)]

## <a name="carchivewritestring"></a><a name="writestring"></a> CArchive:: WriteString

Bir arabellekteki verileri nesneyle ilişkili dosyaya yazmak için bu üye işlevini kullanın `CArchive` .

```cpp
void WriteString(LPCTSTR lpsz);
```

### <a name="parameters"></a>Parametreler

*lpsz*<br/>
Null ile sonlandırılmış metin dizesi içeren bir arabelleğin işaretçisini belirtir.

### <a name="remarks"></a>Açıklamalar

Sonlandırıcı null karakteri (' \ 0 ') dosyaya yazılmadı; ya da otomatik olarak yazılmış bir yeni satır.

`WriteString` disk tam koşulu da dahil olmak üzere çeşitli koşullara yanıt olarak bir özel durum oluşturur.

`Write` Ayrıca kullanılabilir, ancak null bir karakter üzerinde sonlandırılmaktansa, istenen bayt sayısını dosyaya yazar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCSerialization#30](../../mfc/codesnippet/cpp/carchive-class_23.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CFile sınıfı](../../mfc/reference/cfile-class.md)<br/>
[CObject sınıfı](../../mfc/reference/cobject-class.md)<br/>
[CSocket sınıfı](../../mfc/reference/csocket-class.md)<br/>
[CSocketFile sınıfı](../../mfc/reference/csocketfile-class.md)
