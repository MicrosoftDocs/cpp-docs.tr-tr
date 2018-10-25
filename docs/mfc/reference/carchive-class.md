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
ms.openlocfilehash: 88ee9a9e81714064798bbfc652200da9061c6fb0
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50059135"
---
# <a name="carchive-class"></a>CArchive sınıfı

Bu nesneler silindikten sonra devam eden bir kalıcı ikili biçimde (genellikle disk depolama) karmaşık ağ nesnelerini kaydetmenizi sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CArchive
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CArchive::CArchive](#carchive)|Oluşturur bir `CArchive` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CArchive::Abort](#abort)|Bir özel durum oluşturmadan bir arşiv kapatır.|
|[CArchive::Close](#close)|Yazılı verileri temizler ve bağlantıları keser `CFile`.|
|[CArchive::Flush](#flush)|Yazılı verileri arşiv ara bellekten temizler.|
|[CArchive::GetFile](#getfile)|Alır `CFile` bu arşiv için nesne işaretçisi.|
|[CArchive::GetObjectSchema](#getobjectschema)|Çağrılabilir `Serialize` işlevi nesnesini seri durumdan çıkarılmakta olan sürümünü belirlemek için.|
|[CArchive::IsBufferEmpty](#isbufferempty)|Arabellek sırasında bir Windows Sockets boşaltıldı olup olmadığını belirler. alma işlemi.|
|[CArchive::IsLoading](#isloading)|Arşiv yüklüyor olup olmadığını belirler.|
|[CArchive::IsStoring](#isstoring)|Arşiv depolama olup olmadığını belirler.|
|[CArchive::MapObject](#mapobject)|Haritadaki dosyaya seri değildir, ancak alt nesnelerinin için başvurmak kullanılabilir nesneleri yerleştirir.|
|[CArchive::Read](#read)|Ham bayt okur.|
|[CArchive::ReadClass](#readclass)|Sınıf başvurusu daha önce depolanan ile okuma `WriteClass`.|
|[CArchive::ReadObject](#readobject)|Bir nesnenin çağırır `Serialize` yüklenmesi için işlevi.|
|[CArchive::ReadString](#readstring)|Tek satırlık metin okur.|
|[CArchive::SerializeClass](#serializeclass)|Okur veya yazar sınıf başvurusu `CArchive` yöne bağlı olarak nesne `CArchive`.|
|[CArchive::SetLoadParams](#setloadparams)|İstediğiniz yük dizi büyüdükçe boyutunu ayarlar. Herhangi bir nesne yüklenmeden önce ya da önce çağrılmalıdır `MapObject` veya `ReadObject` çağrılır.|
|[CArchive::SetObjectSchema](#setobjectschema)|Arşiv nesnesinde depolanan nesne şemasının ayarlar.|
|[CArchive::SetStoreParams](#setstoreparams)|Karma tablo boyutu ve benzersiz nesne serileştirme işlemi sırasında tanımlamak için kullanılan harita blok boyutunu ayarlar.|
|[CArchive::Write](#write)|Ham bayt yazar.|
|[CArchive::WriteClass](#writeclass)|Bir başvuru Yazar `CRuntimeClass` için `CArchive`.|
|[CArchive::WriteObject](#writeobject)|Bir nesnenin çağırır `Serialize` depolamak için işlevi.|
|[CArchive::WriteString](#writestring)|Tek satırlık metin yazar.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CArchive::operator &lt;&lt;](#operator_lt_lt)|Nesneler ve basit türler arşivi depolar.|
|[CArchive::operator &gt;&gt;](#operator_gt_gt)|Nesneler ve basit türler arşivden yükler.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CArchive::m_pDocument](#m_pdocument)||

## <a name="remarks"></a>Açıklamalar

`CArchive` bir temel sınıfa sahip değil.

Daha sonra bunları bellekte reconstituting kalıcı depolama alanından nesneler yükleyebilirsiniz. Bu işlem, verilerin kalıcı hale getirme "serileştirme." denir.

Bir arşiv nesne bir ikili akış olarak düşünebilirsiniz. Bir giriş/çıkış akışı gibi bir arşiv dosya ile ilişkilendirilmiş ve depolamaya ve depolamadan veri okuma ve yazma arabelleğe alınan izin verir. Bir giriş/çıkış akışı ASCII karakter dizileri işler, ancak bir arşiv verimli, nonredundant biçimde İkili nesne verilerini işler.

Oluşturmalısınız bir [CFile](../../mfc/reference/cfile-class.md) oluşturabilmeniz için önce nesne bir `CArchive` nesne. Ayrıca, arşivin yükleme depolama durumu dosya açık modu ile uyumlu olduğundan emin olmalısınız. Dosya başına bir etkin arşiv sınırlı olmalıdır.

Oluşturduğunuzda bir `CArchive` nesnesi, eklediğiniz bu sınıfın bir nesnesi için `CFile` (veya türetilmiş bir sınıf) açık bir dosyayı temsil eden. Ayrıca, Arşiv yüklenirken veya depolamak için kullanılıp kullanılmayacağını belirtin. A `CArchive` nesne yalnızca ilkel türler aynı zamanda nesnelerin işleyebilir [CObject](../../mfc/reference/cobject-class.md)-türetilmiş sınıfları seri hale getirme için tasarlanmıştır. Seri hale getirilebilir bir sınıf genellikle sahip bir `Serialize` üye işlevi ve genellikle kullanır [declare_serıal](../../mfc/reference/run-time-object-model-services.md#declare_serial) ve [ımplement_serıal](../../mfc/reference/run-time-object-model-services.md#implement_serial) sınıfı altında açıklandığı gibi makrolar `CObject`.

Aşırı yüklenmiş çıkarma ( **>>**) ve ekleme ( **<<**) işleçleridir hem ilkel türler destekleyen uygun arşiv programlama arabirimleri ve `CObject` -türetilmiş sınıflar.

`CArchive` Ayrıca, Windows Sockets MFC sınıfları ile programlama destekler [CSocket](../../mfc/reference/csocket-class.md) ve [CSocketFile](../../mfc/reference/csocketfile-class.md). [IsBufferEmpty](#isbufferempty) üye işlevi bu kullanımını destekler.

Daha fazla bilgi için `CArchive`, makalelere göz atın [serileştirme](../../mfc/serialization-in-mfc.md) ve [Windows Yuvaları: yuvaların arşivlerle kullanma](../../mfc/windows-sockets-using-sockets-with-archives.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CArchive`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afx.h

##  <a name="abort"></a>  CArchive::Abort

Bir özel durum oluşturmadan arşiv kapatmak için bu işlevi çağırın.

```
void Abort ();
```

### <a name="remarks"></a>Açıklamalar

`CArchive` Yok Edicisi normalde çağıracaktır `Close`, hangi kaydedilmemiş herhangi bir veri temizleme ilişkili için `CFile` nesne. Bu, özel durumlar neden olabilir.

Bu özel durumları yakalama, bunu kullanmak için iyi bir fikirdir `Abort`, böylece destructing `CArchive` nesnesi değil neden daha ayrıntılı özel durumlar. Özel durumlar, işlerken `CArchive::Abort` bir özel durum nedeniyle hatalarında oluşturmayacaksa aksine [CArchive::Close](#close), `Abort` hatalarını yok sayar.

Kullandıysanız **yeni** ayrılacak `CArchive` dosya kapattıktan sonra silmelisiniz yığında nesne.

### <a name="example"></a>Örnek

  Örneğin bakın [CArchive::WriteClass](#writeclass).

##  <a name="carchive"></a>  CArchive::CArchive

Oluşturur bir `CArchive` nesne ve onu yüklenirken veya nesneleri depolamak için kullanılıp kullanılmayacağını belirtir.

```
CArchive(
    CFile* pFile,
    UINT nMode,
    int nBufSize = 4096,
    void* lpBuf = NULL);
```

### <a name="parameters"></a>Parametreler

*pFile*<br/>
Bir işaretçi `CFile` ultimate kaynak veya hedef kalıcı veri nesnesi.

*nMode*<br/>
Nesneleri konumdan yüklendi veya kaldırılacak arşive depolanmış olup olmadığını belirten bir bayrak. *NMode* parametre aşağıdaki değerlerden birine sahip olmalıdır:

- `CArchive::load` Arşivden verileri yükler. Yalnızca gerektirir `CFile` okuma izni.

- `CArchive::store` Verileri arşive kaydeder. Gerektirir `CFile` yazma izni.

- `CArchive::bNoFlushOnDelete` Otomatik olarak çağırma arşiv engeller `Flush` zaman arşiv yok Edicisi çağrılır. Bu bayrağı ayarlarsanız, açıkça çağırmak için sorumlu olduğunuz `Close` önce yok Edicisi çağrılır. Bunu yapmazsanız, verilerinizi bozulacaktır.

*nBufSize*<br/>
Dosya iç arabellek boyutu bayt cinsinden belirten bir tamsayı. Varsayılan arabellek boyutu 4096 bayt olduğunu unutmayın. Düzenli olarak büyük nesneler arşivlerseniz, dosya arabelleğinin katları olan daha büyük bir arabellek boyutu kullanırsanız performansı iyileştirir.

*lpBuf*<br/>
Bir kullanıcı tarafından sağlanan arabellek boyutunu isteğe bağlı işaretçisi *nBufSize*. Bu parametreyi belirtmezseniz, arşiv yerel öbek arabelleğinden ayırır ve nesneye kaldırıldığında serbest bırakır. Arşiv, bir kullanıcı tarafından sağlanan arabellek boş değil.

### <a name="remarks"></a>Açıklamalar

Bu belirtim, arşiv oluşturduktan sonra değiştiremezsiniz.

Seçeneğini kullanmaz `CFile` arşiv kapatıncaya kadar dosya durumunu değiştirmek için işlem. Herhangi bir işlem arşiv bütünlüğünü zarar. Arşivin dosya nesneden elde ederek serileştirme sırasında herhangi bir zamanda dosya işaretçisi konumunu erişebilir [DosyaAl](#getfile) üye işlevi ve ardından kullanarak [CFile::GetPosition](../../mfc/reference/cfile-class.md#getposition) işlevi . Çağırmalısınız [CArchive::Flush](#flush) önce dosya işaretçisi konumunu alma.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCSerialization#12](../../mfc/codesnippet/cpp/carchive-class_1.cpp)]

##  <a name="close"></a>  CArchive::Close

Arabelleğinde kalan tüm verileri temizler, arşiv kapatır ve Arşiv dosyasından bağlantısını keser.

```
void Close();
```

### <a name="remarks"></a>Açıklamalar

Başka işlem arşiv üzerinde izin verilir. Bir arşiv kapattıktan sonra aynı dosya için başka bir arşiv oluşturabilirsiniz veya dosya kapatabilirsiniz.

Üye işlevi `Close` tüm verileri arşivden dosyasına aktarılır ve Arşiv onu kullanılamaz yapar sağlar. Depolama ortamı için dosya aktarımı tamamlamak için önce kullanmalısınız [CFile::Close](../../mfc/reference/cfile-class.md#close) ve ardından yok `CFile` nesne.

### <a name="example"></a>Örnek

  Örneğin bakın [CArchive::WriteString](#writestring).

##  <a name="flush"></a>  CArchive::Flush

Dosyaya yazılacak arşiv arabelleğinde kalan herhangi bir veri zorlar.

```
void Flush();
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi `Flush` tüm veri aktarılır, arşivden dosyaya sağlar. Çağırmalısınız [CFile::Close](../../mfc/reference/cfile-class.md#close) dosyasından depolama ortamına aktarımı tamamlamak için.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCSerialization#13](../../mfc/codesnippet/cpp/carchive-class_2.cpp)]

##  <a name="getfile"></a>  CArchive::GetFile

Alır `CFile` bu arşiv için nesne işaretçisi.

```
CFile* GetFile() const;
```

### <a name="return-value"></a>Dönüş Değeri

İçin sabit bir işaretçi `CFile` kullanılan nesne.

### <a name="remarks"></a>Açıklamalar

Kullanmadan önce arşiv temizleme gerekir `GetFile`.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCSerialization#14](../../mfc/codesnippet/cpp/carchive-class_3.cpp)]

##  <a name="getobjectschema"></a>  CArchive::GetObjectSchema

Bu bir işlevden çağırma `Serialize` işlevi şu anda seri durumdan çıkarılmakta olan nesne sürümü belirlenemedi.

```
UINT GetObjectSchema();
```

### <a name="return-value"></a>Dönüş Değeri

Seri durumundan çıkarma sırasında okunan nesne sürümü.

### <a name="remarks"></a>Açıklamalar

Bu işlevi çağırmak, yalnızca geçerli zaman `CArchive` nesne yüklenme ( [CArchive::IsLoading](#isloading) sıfır döndürür). İlk çağrıda olmalıdır `Serialize` işlevi ve adlı yalnızca bir kez. Dönüş değeri (birim) -1, sürüm numarasını bilinmediğini gösterir.

A `CObject`-türetilmiş sınıf, birleştirilmiş versıonable_schema kullanabilir (bit düzeyinde kullanarak **veya**) şema sürümünde kendisi (ımplement_serıal makrosu) ile bir "sürümlenebilir nesnesi," diğer bir deyişle, bir nesne oluşturmak için `Serialize` üye işlevi, birden çok sürümünü okuyabilirsiniz. Varsayılan framework (olmadan versıonable_schema) sürümü uyumsuz olduğunda, bir özel durum için bir işlevdir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCSerialization#15](../../mfc/codesnippet/cpp/carchive-class_4.cpp)]

##  <a name="isbufferempty"></a>  CArchive::IsBufferEmpty

Arşiv nesnenin iç arabellek boş olup olmadığını belirlemek için bu üye işlevini çağırın.

```
BOOL IsBufferEmpty() const;
```

### <a name="return-value"></a>Dönüş Değeri

Arşivin arabellek boş ise sıfır olmayan; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev, Windows Sockets MFC sınıfı ile programlamayı desteklemek için sağlanan `CSocketFile`. İle ilişkili bir arşiv kullanılmak üzere gerekmez bir `CFile` nesne.

Kullanılmasının nedeni `IsBufferEmpty` ile ilişkili bir arşiv bir `CSocketFile` nesnedir arşivin arabellek birden fazla ileti veya kayıt içerebilir. Bir iletiyi aldıktan sonra kullanmanız gereken `IsBufferEmpty` arabellek boş olana kadar veri almaya devam eden bir döngüyü denetlemek üzere. Daha fazla bilgi için [alma](../../mfc/reference/casyncsocket-class.md#receive) sınıfının üye işlevinde `CAsyncSocket`, nasıl kullanılacağını göstermektedir `IsBufferEmpty`.

Daha fazla bilgi için [Windows Yuvaları: yuvaların arşivlerle kullanma](../../mfc/windows-sockets-using-sockets-with-archives.md).

##  <a name="isloading"></a>  CArchive::IsLoading

Arşiv verileri yüklüyor olup olmadığını belirler.

```
BOOL IsLoading() const;
```

### <a name="return-value"></a>Dönüş Değeri

Arşiv yüklenmesi için şu anda kullanılıyor olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi çağıran `Serialize` arşivlenmiş sınıfların işlevleri.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCSerialization#16](../../mfc/codesnippet/cpp/carchive-class_5.cpp)]

##  <a name="isstoring"></a>  CArchive::IsStoring

Arşiv verileri depolama olup olmadığını belirler.

```
BOOL IsStoring() const;
```

### <a name="return-value"></a>Dönüş Değeri

Arşiv depolama için şu anda kullanılıyor olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi çağıran `Serialize` arşivlenmiş sınıfların işlevleri.

Varsa `IsStoring` bir arşiv durumu sıfır olmayan, ardından kendi `IsLoading` durumu: 0 ve bunun tersi de geçerlidir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCSerialization#17](../../mfc/codesnippet/cpp/carchive-class_6.cpp)]

##  <a name="mapobject"></a>  CArchive::MapObject

Harita, gerçekten dosyaya serileştirilen değil, ancak alt nesnelerinin için başvurmak kullanılabilir nesneleri yerleştirmek için bu üye işlevini çağırın.

```
void MapObject(const CObject* pOb);
```

### <a name="parameters"></a>Parametreler

*posta kutusu*<br/>
Depolanmakta olan nesne için sabit bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Örneğin, bir belge serileştirilecek değil, ancak belgeyi bir parçası olan öğeleri seri hale getirmek. Çağırarak `MapObject`, bu öğeleri veya belge başvurmak için alt nesnelerinin izin verin. Ayrıca, seri hale getirilmiş bir alt öğesi serileştirebiliyorsa kendi *m_pDocument* geri işaretçisi.

Çağırabilirsiniz `MapObject` , depolama ve yükleme `CArchive` nesne. `MapObject` Belirtilen nesne tarafından tutulan iç veri yapılarını ekler `CArchive` nesne seri hale getirme ve seri durumundan çıkarma sırasında ancak farklı [ReadObject](#readobject) ve [WriteObject](#writeobject), arama nesnede seri hale.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCSerialization#18](../../mfc/codesnippet/cpp/carchive-class_7.h)]

[!code-cpp[NVC_MFCSerialization#19](../../mfc/codesnippet/cpp/carchive-class_8.cpp)]

[!code-cpp[NVC_MFCSerialization#20](../../mfc/codesnippet/cpp/carchive-class_9.h)]

[!code-cpp[NVC_MFCSerialization#21](../../mfc/codesnippet/cpp/carchive-class_10.cpp)]

##  <a name="m_pdocument"></a>  CArchive::m_pDocument

Varsayılan olarak, bu işaretçi NULL olarak ayarlamak bir `CDocument` kullanıcısı için bir şey ayarlanabilir `CArchive` istediği örneği.

```
CDocument* m_pDocument;
```

### <a name="remarks"></a>Açıklamalar

Serileştirilmekte olan tüm nesneleri için seri hale getirme işlemi hakkında ek bilgiler iletmek için bir ortak kullanımı da, bu işaretçi var. Bu belge işaretçiyle başlatarak sağlanır (bir `CDocument`-türetilmiş sınıf), serileştirildiği, belge içindeki nesneleri gerekirse belgeye erişemez yolu. Bu işaretçi tarafından da kullanılan `COleClientItem` serileştirme sırasında nesneleri.

Framework kümeleri *m_pDocument* bir kullanıcı bir dosyayı verdiğinde serileştirilmekte olan belgeyi açın veya Farklı Kaydet komutu. Bir nesne bağlama ve Katıştırma (OLE) kapsayıcı belgesi dosyasını açın veya Kaydet farklı nedenlerle sıralarsanız, açıkça ayarlamalısınız *m_pDocument*. Örneğin, bir kapsayıcı belge panoya serileştirilirken bunu.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCSerialization#35](../../mfc/codesnippet/cpp/carchive-class_11.cpp)]

##  <a name="operator_lt_lt"></a>  CArchive::operator &lt;&lt;

Belirtilen nesneyi veya ilkel tür arşivi depolar.

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

A `CArchive` tek bir satırda birden çok ekleme işleçlerini sağlayan bir başvuru.

### <a name="remarks"></a>Açıklamalar

Son iki yukarıdaki 64-bit tamsayıya depolamak için özel olarak sürümleridir.

Implement_serıal makrosu sınıfı uygulamanızda kullanılan sonra için ekleme işleci aşırı `CObject` korumalı çağırır `WriteObject`. Sırayla bu işlevi çağıran `Serialize` işlevi sınıf.

[CStringT](../../atl-mfc-shared/reference/cstringt-class.md) ekleme operatörü (<<) tanılama dökme ve arşive depolama destekler.

### <a name="example"></a>Örnek

Bu örnek kullanımını gösterir `CArchive` ekleme işleci << ile **int** ve **uzun** türleri.

[!code-cpp[NVC_MFCSerialization#31](../../mfc/codesnippet/cpp/carchive-class_12.cpp)]

### <a name="example"></a>Örnek

2. Bu örnek kullanımını gösterir `CArchive` ekleme işleci << ile `CStringT` türü.

[!code-cpp[NVC_MFCSerialization#32](../../mfc/codesnippet/cpp/carchive-class_13.cpp)]

##  <a name="operator_gt_gt"></a>  CArchive::operator &gt;&gt;

Belirtilen nesne veya basit tür arşivden yükler.

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

A `CArchive` sağlayan tek bir satırda birden çok ayıklama işleç başvurusu.

### <a name="remarks"></a>Açıklamalar

Son iki yukarıdaki özellikle 64-bit tamsayıya yüklemek için sürümleridir.

Implement_serıal makrosu sınıfı uygulamanızda kullanılan sonra çıkarma işleçleri için aşırı yüklenmiş `CObject` korumalı çağrı `ReadObject` işlevi (sıfır olmayan bir çalışma zamanı sınıf işaretçisiyle). Sırayla bu işlevi çağıran `Serialize` işlevi sınıf.

[CStringT](../../atl-mfc-shared/reference/cstringt-class.md) çıkarma işleci (>>) arşivden yüklemeyi destekliyor.

### <a name="example"></a>Örnek

Bu örnek kullanımını gösterir `CArchive` ayıklama işleci >> ile **int** türü.

[!code-cpp[NVC_MFCSerialization#33](../../mfc/codesnippet/cpp/carchive-class_14.cpp)]

### <a name="example"></a>Örnek

Bu örnek kullanımını gösterir `CArchive` ekleme ve çıkarma işleçleri <\< ve >> ile `CStringT` türü.

[!code-cpp[NVC_MFCSerialization#34](../../mfc/codesnippet/cpp/carchive-class_15.cpp)]

##  <a name="read"></a>  CArchive::Read

Belirtilen sayıda baytı bir arşivden okur.

```
UINT Read(void* lpBuf, UINT nMax);
```

### <a name="parameters"></a>Parametreler

*lpBuf*<br/>
Verileri almak için bir kullanıcı tarafından sağlanan arabellek için işaretçi arşivden okur.

*nMax*<br/>
Arşivden okunacak bayt sayısını belirten bir işaretsiz tamsayı.

### <a name="return-value"></a>Dönüş Değeri

Aslında okunan bayt sayısını içeren bir işaretsiz tamsayı. Dönüş değeri İstenen sayıdan daha az ise, dosya sonuna ulaşıldı. Dosya sonu koşulu üzerinde hiçbir özel durum oluşturulur.

### <a name="remarks"></a>Açıklamalar

Arşiv bayt yorumlamaz.

Kullanabileceğiniz `Read` içindeki üye işlevi, `Serialize` , nesnelerin içindeki normal yapıları okumak için kullanılan işlev.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCSerialization#24](../../mfc/codesnippet/cpp/carchive-class_16.cpp)]

##  <a name="readclass"></a>  CArchive::ReadClass

Bir sınıf ile daha önce depolanan başvuru okumak için bu üye işlevini çağırın [WriteClass](#writeclass).

```
CRuntimeClass* ReadClass(
    const CRuntimeClass* pClassRefRequested = NULL,
    UINT* pSchema = NULL,
    DWORD* pObTag = NULL);
```

### <a name="parameters"></a>Parametreler

*pClassRefRequested*<br/>
Bir işaretçi [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) istenen sınıf başvurusu karşılık gelen yapısı. NULL olabilir.

*pSchema*<br/>
Daha önce depolanan çalışma zamanı sınıfının bir şema için bir işaretçi.

*pObTag*<br/>
Bir nesnenin benzersiz etiket için başvuran bir sayı. Uygulaması tarafından dahili olarak kullanılan [ReadObject](#readobject). Yalnızca Gelişmiş programlama için kullanıma sunulan; *pObTag* normalde NULL olmalıdır.

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) yapısı.

### <a name="remarks"></a>Açıklamalar

Varsa *pClassRefRequested* NULL değil `ReadClass` arşivlenmiş sınıf bilgilerini, çalışma zamanı sınıfı ile uyumlu olduğunu doğrular. Uyumlu değilse `ReadClass` oluşturmaz bir [CArchiveException](../../mfc/reference/carchiveexception-class.md).

Çalışma zamanı sınıfınıza kullanmalısınız [declare_serıal](../../mfc/reference/run-time-object-model-services.md#declare_serial) ve [ımplement_serıal](../../mfc/reference/run-time-object-model-services.md#implement_serial); Aksi takdirde `ReadClass` oluşturmaz bir [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).

Varsa *pSchema* NULL ise saklı sınıfın şemasıyla çağrılarak alınabilir [CArchive::GetObjectSchema](#getobjectschema); Aksi takdirde <strong>\*</strong>  *pSchema* daha önce depolanan çalışma zamanı sınıf şemasını içerir.

Kullanabileceğiniz [SerializeClass](#serializeclass) yerine `ReadClass`, hem okumaya hem yazmaya sınıf başvurusu işler.

### <a name="example"></a>Örnek

  Örneğin bakın [CArchive::WriteClass](#writeclass).

##  <a name="readobject"></a>  CArchive::ReadObject

Nesne verilerini bir arşivden okur ve uygun türde bir nesne oluşturur.

```
CObject* ReadObject(const CRuntimeClass* pClass);
```

### <a name="parameters"></a>Parametreler

*pClass*<br/>
İçin sabit bir işaretçi [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) beklediğiniz okumak için nesneye karşılık gelen yapısı.

### <a name="return-value"></a>Dönüş Değeri

A [CObject](../../mfc/reference/cobject-class.md) güvenli bir şekilde doğru dönüştürülmelidir işaretçisi türetilmiş sınıf kullanarak [CObject::IsKindOf](../../mfc/reference/cobject-class.md#iskindof).

### <a name="remarks"></a>Açıklamalar

Bu işlev normal olarak çağıran `CArchive` ayıklama ( **>>**) işleci aşırı için bir [CObject](../../mfc/reference/cobject-class.md) işaretçi. `ReadObject`, buna karşılık, çağıran `Serialize` arşivlenmiş sınıfının işlevi.

Sıfır dışında bir sağlarsanız *pClass* ile alınan parametresini [RUNTIME_CLASS](../../mfc/reference/run-time-object-model-services.md#runtime_class) makrosu, ardından işlevin arşivlenmiş nesnenin çalışma zamanı sınıfı doğrular. Bu sınıfın uygulamasında ımplement_serıal makrosu kullandığınızı varsayar.

### <a name="example"></a>Örnek

  Örneğin bakın [CArchive::WriteObject](#writeobject).

##  <a name="readstring"></a>  CArchive::ReadString

Bir arabelleğine ilişkili dosyasından metin verileri okumak için bu üye işlevi çağrısı `CArchive` nesne.

```
BOOL ReadString(CString& rString);
LPTSTR ReadString(LPTSTR lpsz, UINT nMax);
```

### <a name="parameters"></a>Parametreler

*rString*<br/>
Bir başvuru bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) CArchive nesneyle ilişkili dosyasından okuduktan sonra sonuç dize içerecek.

*lpsz*<br/>
Bir metin null ile sonlandırılmış dize alacak bir kullanıcı tarafından sağlanan arabellek için işaretçi belirtir.

*nMax*<br/>
Okunacak karakter maksimum sayısını belirtir. Bir olmalıdır boyutu küçüktür *lpsz* arabellek.

### <a name="return-value"></a>Dönüş Değeri

BOOL, başarılı olursa TRUE değeri döndürür sürümünde; FALSE Aksi takdirde.

Döndüren sürümündeki bir `LPTSTR`, arabellek için metin verilerini içeren bir işaretçi Dosya sonu ulaşıldı yoksa NULL.

### <a name="remarks"></a>Açıklamalar

Üye işlevini sürümünde *nMax* parametresi, arabellek tutun için bir sınır *nMax* - 1 karakter. Okuma bir satır başı satır besleme çifti tarafından durduruldu. İzleyen yeni satır karakteri her zaman kaldırılır. Null karakteri ('\0'), her iki durumda da eklenir.

[CArchive::Read](#read) metin modunda girdi, ancak değil sonlandırmak için bir satır başı satır besleme çiftine de kullanılabilir.

### <a name="example"></a>Örnek

  Örneğin bakın [CArchive::WriteString](#writestring).

##  <a name="serializeclass"></a>  CArchive::SerializeClass

Depolayın ve sürüm bilgilerini bir taban sınıfın yüklemek istediğinizde, bu üye işlevini çağırın.

```
void SerializeClass(const CRuntimeClass* pClassRef);
```

### <a name="parameters"></a>Parametreler

*pClassRef*<br/>
Temel sınıf için bir çalışma zamanı sınıf nesnesine bir işaretçi.

### <a name="remarks"></a>Açıklamalar

`SerializeClass` okuyan veya yazan bir sınıfa başvuru `CArchive` yöne bağlı olarak bir nesne `CArchive`. Kullanım `SerializeClass` yerine [ReadClass](#readclass) ve [WriteClass](#writeclass) ; taban sınıfı nesneleri serileştirmek için kullanışlı bir yol olarak `SerializeClass` daha az kod ve daha az parametre gerektirir.

Gibi `ReadClass`, `SerializeClass` arşivlenmiş sınıf bilgilerini, çalışma zamanı sınıfı ile uyumlu olduğunu doğrular. Uyumlu değilse `SerializeClass` oluşturmaz bir [CArchiveException](../../mfc/reference/carchiveexception-class.md).

Çalışma zamanı sınıfınıza kullanmalısınız [declare_serıal](../../mfc/reference/run-time-object-model-services.md#declare_serial) ve [ımplement_serıal](../../mfc/reference/run-time-object-model-services.md#implement_serial); Aksi takdirde `SerializeClass` oluşturmaz bir [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).

Kullanım [RUNTIME_CLASS](../../mfc/reference/run-time-object-model-services.md#runtime_class) değerini almak için makro *pRuntimeClass* parametresi. Temel sınıf kullanılan [ımplement_serıal](../../mfc/reference/run-time-object-model-services.md#implement_serial) makrosu.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCSerialization#25](../../mfc/codesnippet/cpp/carchive-class_17.h)]

##  <a name="setloadparams"></a>  CArchive::SetLoadParams

Çağrı `SetLoadParams` zaman seçeceğiz çok sayıda okunacak `CObject`-arşivden türetilmiş nesneler.

```
void SetLoadParams(UINT nGrowBy = 1024);
```

### <a name="parameters"></a>Parametreler

*nGrowBy*<br/>
Öğe yuvaları boyutu artışı gerekliyse ayrılacak en küçük sayısı.

### <a name="remarks"></a>Açıklamalar

`CArchive` Arşiv'de depolanan nesnelere başvuruları çözümlemek için bir yük dizisini kullanır. `SetLoadParams` istediğiniz yük dizi büyüdükçe boyutu ayarlamanıza olanak tanır.

Çağrılmayan gerekir `SetLoadParams` herhangi bir nesne yüklendikten sonra veya sonrasında [MapObject](#mapobject) veya [ReadObject](#readobject) çağrılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCSerialization#26](../../mfc/codesnippet/cpp/carchive-class_18.h)]

##  <a name="setobjectschema"></a>  CArchive::SetObjectSchema

Arşiv nesnesindeki depolanan nesne şemasının ayarlamak için bu üye işlevi çağrısı *nSchema*.

```
void SetObjectSchema(UINT nSchema);
```

### <a name="parameters"></a>Parametreler

*nSchema*<br/>
Nesnenin şema belirtir.

### <a name="remarks"></a>Açıklamalar

Sonraki çağrı [GetObjectSchema](#getobjectschema) içinde depolanan değeri döndüreceği *nSchema*.

Kullanım `SetObjectSchema` Gelişmiş sürüm oluşturma için; örneğin, zaman içinde okumak için belirli bir sürümü zorlamak istiyorsanız bir `Serialize` türetilmiş bir sınıfın işlevi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCSerialization#27](../../mfc/codesnippet/cpp/carchive-class_19.cpp)]

##  <a name="setstoreparams"></a>  CArchive::SetStoreParams

Kullanım `SetStoreParams` çok sayıda depolarken `CObject`-türetilmiş bir arşiv nesneleri.

```
void SetStoreParams(UINT nHashSize = 2053, UINT nBlockSize = 128);
```

### <a name="parameters"></a>Parametreler

*nHashSize*<br/>
Arabirim işaretçisi için karma tablo boyutu eşler. Asal olmalıdır.

*nBlockSize*<br/>
Parametreleri genişletmek için bellek ayırma ayrıntı düzeyi belirtir. En iyi performans için 2'in üssü olmalıdır.

### <a name="remarks"></a>Açıklamalar

`SetStoreParams` Karma tablo boyutu ve blok boyutu benzersiz nesne serileştirme işlemi sırasında tanımlamak için kullanılan harita ayarlamanıza olanak tanır.

Çağrılmayan gerekir `SetStoreParams` herhangi bir nesne depolandıktan sonra veya sonrasında [MapObject](#mapobject) veya [WriteObject](#writeobject) çağrılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCSerialization#26](../../mfc/codesnippet/cpp/carchive-class_18.h)]

##  <a name="write"></a>  CArchive::Write

Belirtilen sayıda baytı arşive yazar.

```
void Write(const void* lpBuf, INT nMax);
```

### <a name="parameters"></a>Parametreler

*lpBuf*<br/>
Arşive yazılacak veriler içeren bir kullanıcı tarafından sağlanan arabellek için bir işaretçi.

*nMax*<br/>
Arşive yazılacak bayt sayısını belirten bir tamsayı.

### <a name="remarks"></a>Açıklamalar

Arşiv bayt biçiminde değil.

Kullanabileceğiniz `Write` içindeki üye işlevi, `Serialize` sıradan yapıları yazılacak işlev nesnelerinizi içinde yer alır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCSerialization#23](../../mfc/codesnippet/cpp/carchive-class_20.cpp)]

##  <a name="writeclass"></a>  CArchive::WriteClass

Kullanım `WriteClass` türetilmiş sınıfın serileştirme sırasında bir taban sınıfın sürümü ve sınıf bilgileri depolamak için.

```
void WriteClass(const CRuntimeClass* pClassRef);
```

### <a name="parameters"></a>Parametreler

*pClassRef*<br/>
Bir işaretçi [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) istenen sınıf başvurusu karşılık gelen yapısı.

### <a name="remarks"></a>Açıklamalar

`WriteClass` bir başvuru Yazar [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) için temel sınıf için `CArchive`. Kullanım [CArchive::ReadClass](#readclass) başvuru alınamıyor.

`WriteClass` Arşivlenen sınıf bilgilerini, çalışma zamanı sınıfı ile uyumlu olduğunu doğrular. Uyumlu değilse `WriteClass` oluşturmaz bir [CArchiveException](../../mfc/reference/carchiveexception-class.md).

Çalışma zamanı sınıfınıza kullanmalısınız [declare_serıal](../../mfc/reference/run-time-object-model-services.md#declare_serial) ve [ımplement_serıal](../../mfc/reference/run-time-object-model-services.md#implement_serial); Aksi takdirde `WriteClass` oluşturmaz bir [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).

Kullanabileceğiniz [SerializeClass](#serializeclass) yerine `WriteClass`, hem okumaya hem yazmaya sınıf başvurusu işler.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCSerialization#28](../../mfc/codesnippet/cpp/carchive-class_21.cpp)]

##  <a name="writeobject"></a>  CArchive::WriteObject

Belirtilen depolar `CObject` arşivi.

```
void WriteObject(const CObject* pOb);
```

### <a name="parameters"></a>Parametreler

*posta kutusu*<br/>
Depolanmakta olan nesne için sabit bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu işlev normal olarak çağıran `CArchive` ekleme ( **<<**) işleci aşırı için `CObject`. `WriteObject`, buna karşılık, çağıran `Serialize` arşivlenmiş sınıfının işlevi.

Implement_serıal makrosu arşivleme etkinleştirmek için kullanmanız gerekir. `WriteObject` ASCII sınıf adı, arşiv için yazar. Bu sınıf adı, daha sonra yükleme işlemi sırasında doğrulanır. Özel bir kodlama düzeni, birden çok nesne sınıfı için sınıf adı gereksiz yinelenmesini önler. Bu düzen aynı zamanda birden fazla işaretçi hedefleri olan nesneler olarak yedekli engeller.

Kodlama yöntemini (ASCII sınıf adı varlığını dahil olmak üzere) tam nesne bir uygulama ayrıntısı ve kitaplık sürümleri gelecekte değişebilir.

> [!NOTE]
>  Oluşturma, silme ve onları arşivlemek başlamadan önce tüm nesneleri güncelleştirme tamamlayın. Nesne değişikliği arşivleme karışımı varsa, arşiv bozuk.

### <a name="example"></a>Örnek

Sınıf tanımı için `CAge`, örneğin bakın [CObList::CObList](../../mfc/reference/coblist-class.md#coblist).

[!code-cpp[NVC_MFCSerialization#29](../../mfc/codesnippet/cpp/carchive-class_22.cpp)]

##  <a name="writestring"></a>  CArchive::WriteString

Veri ilişkili dosya bir arabellek yazmak için bu üye işlevi kullanın `CArchive` nesne.

```
void WriteString(LPCTSTR lpsz);
```

### <a name="parameters"></a>Parametreler

*lpsz*<br/>
Bir metin null ile sonlandırılmış dize içeren arabellek için işaretçi belirtir.

### <a name="remarks"></a>Açıklamalar

Sondaki boş karakter ('\0') dosyasına yazılır değil; ya da yeni bir satır otomatik olarak yazılır.

`WriteString` yanıt olarak disk dolu koşulu dahil olmak üzere çeşitli koşullar, özel durum oluşturur.

`Write` Ayrıca, kullanılabilir ancak bir null karakteri sonlandırarak yerine, istenen bayt sayısını dosyasına yazar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCSerialization#30](../../mfc/codesnippet/cpp/carchive-class_23.cpp)]

## <a name="see-also"></a>Ayrıca Bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CFile Sınıfı](../../mfc/reference/cfile-class.md)<br/>
[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[CSocket Sınıfı](../../mfc/reference/csocket-class.md)<br/>
[CSocketFile Sınıfı](../../mfc/reference/csocketfile-class.md)
