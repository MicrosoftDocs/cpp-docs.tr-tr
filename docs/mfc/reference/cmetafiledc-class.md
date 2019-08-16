---
title: CMetaFileDC sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMetaFileDC
- AFXEXT/CMetaFileDC
- AFXEXT/CMetaFileDC::CMetaFileDC
- AFXEXT/CMetaFileDC::Close
- AFXEXT/CMetaFileDC::CloseEnhanced
- AFXEXT/CMetaFileDC::Create
- AFXEXT/CMetaFileDC::CreateEnhanced
helpviewer_keywords:
- CMetaFileDC [MFC], CMetaFileDC
- CMetaFileDC [MFC], Close
- CMetaFileDC [MFC], CloseEnhanced
- CMetaFileDC [MFC], Create
- CMetaFileDC [MFC], CreateEnhanced
ms.assetid: ffce60fa-4181-4d46-9832-25e46fad4db4
ms.openlocfilehash: 61e8442c085a5be0a7266409daf973bf63f52a7f
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69505513"
---
# <a name="cmetafiledc-class"></a>CMetaFileDC sınıfı

İstenen bir görüntü veya metin oluşturmak için yeniden yürütebilmeniz gereken bir grafik cihaz arabirimi (GDI) komutları dizisi içeren bir Windows meta dosyası uygular.

## <a name="syntax"></a>Sözdizimi

```
class CMetaFileDC : public CDC
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMetaFileDC:: CMetaFileDC](#cmetafiledc)|Bir `CMetaFileDC` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMetaFileDC:: Close](#close)|Cihaz bağlamını kapatır ve bir meta dosyası tutamacı oluşturur.|
|[CMetaFileDC:: CloseEnhanced](#closeenhanced)|Gelişmiş bir dosya cihazı bağlamını kapatır ve gelişmiş bir dosya tutamacı oluşturur.|
|[CMetaFileDC:: Create](#create)|Windows meta dosyası cihaz bağlamını oluşturur ve `CMetaFileDC` nesneye ekler.|
|[CMetaFileDC:: CreateEnhanced](#createenhanced)|Gelişmiş biçimdeki meta dosya için bir meta dosyası cihaz bağlamı oluşturur.|

## <a name="remarks"></a>Açıklamalar

Bir Windows meta dosyası uygulamak için öncelikle bir `CMetaFileDC` nesne oluşturun. Oluşturucuyu çağırın, sonra bir Windows meta [](#create) dosyası cihaz bağlamı oluşturup bunu `CMetaFileDC` nesnesine bağlayan üye Oluştur işlevini çağırın. `CMetaFileDC`

Sonra nesneyi, `CMetaFileDC` yeniden oynadığınız CDC GDI komutlarının dizisini gönderin. Yalnızca, `MoveTo` ve `LineTo`gibi çıkış oluşturan GDI komutları kullanılabilir.

İstenen komutları meta dosyasına gönderdikten sonra, meta dosyası cihaz bağlamlarını kapatan `Close` ve bir meta dosyası tanıtıcısı döndüren üye işlevini çağırın. Sonra `CMetaFileDC` nesneyi atın.

[CDC::P layMetaFile](../../mfc/reference/cdc-class.md#playmetafile) , meta dosyası tekrar tekrar oynatmak için meta dosyası tanıtıcısını kullanabilir. Meta dosyası, bir dosya dosyasını diske kopyalayan [CopyMetaFile](/windows/win32/api/wingdi/nf-wingdi-copymetafilew)gibi Windows işlevleri tarafından da yönetilebilir.

Meta dosyası artık gerekli olmadığında, [DeleteMetaFile](/windows/win32/api/wingdi/nf-wingdi-deletemetafile) Windows işleviyle bellekten silin.

Ayrıca, nesnesi gibi hem `CMetaFileDC` çıkış çağrılarını hem de öznitelik GDI çağrılarını `GetTextExtent`işleyebilmesi için nesnesini de uygulayabilirsiniz. Bu tür bir meta dosyası daha esnektir ve genellikle çıkış ve öznitelik çağrılarının karışımından oluşan genel GDI kodunu daha kolay bir şekilde yeniden kullanabilir. Sınıfı iki cihaz `m_hDC` bağlamı devralır ve `m_hAttribDC`CDC 'den. `CMetaFileDC` Cihaz bağlamı tüm [CDC](../../mfc/reference/cdc-class.md) GDI `m_hAttribDC` çıkış çağrılarını işler ve cihaz bağlamı tüm CDC GDI öznitelik çağrılarını işler. `m_hDC` Normalde, bu iki cihaz bağlamı aynı cihaza başvurur. Bu durumda `CMetaFileDC`, dc özniteliği varsayılan olarak null olarak ayarlanır.

Ekran, yazıcı veya dosya dışında bir cihaz gösteren ikinci bir cihaz bağlamı oluşturun ve ardından yeni cihaz bağlamını ile `SetAttribDC` `m_hAttribDC`ilişkilendirmek için üye işlevini çağırın. Bilgiler için GDI çağrıları artık yeni `m_hAttribDC`bir şekilde yönlendirilir. Çıktı GDI çağrıları, meta dosyasını `m_hDC`temsil eden öğesine gidecek.

Hakkında `CMetaFileDC`daha fazla bilgi için bkz. [cihaz bağlamları](../../mfc/device-contexts.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CDC](../../mfc/reference/cdc-class.md)

`CMetaFileDC`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxext. h

##  <a name="close"></a>CMetaFileDC:: Close

Meta dosyası cihaz bağlamını kapatır ve [CDC::P laymetafile](../../mfc/reference/cdc-class.md#playmetafile) üye işlevini kullanarak meta dosyası oynatmak için kullanılabilecek bir Windows meta dosyası tanıtıcısı oluşturur.

```
HMETAFILE Close();
```

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa geçerli bir HMETAFILE; Aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Windows meta dosyası tanıtıcısı, [CopyMetaFile](/windows/win32/api/wingdi/nf-wingdi-copymetafilew)gibi Windows işlevleriyle meta dosyası işlemek için de kullanılabilir.

Windows [DeleteMetaFile](/windows/win32/api/wingdi/nf-wingdi-deletemetafile) işlevini çağırarak, kullandıktan sonra meta dosyası silin.

##  <a name="closeenhanced"></a>CMetaFileDC:: CloseEnhanced

Gelişmiş bir meta dosyası cihaz bağlamını kapatır ve gelişmiş biçimdeki bir meta dosyası tanımlayan bir tanıtıcı döndürür.

```
HENHMETAFILE CloseEnhanced();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, gelişmiş bir meta dosyası tanıtıcısı; Aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Bir uygulama, aşağıdaki görevleri gerçekleştirmek için bu işlev tarafından döndürülen gelişmiş-meta dosya işleyicisini kullanabilir:

- Gelişmiş bir meta dosyasında depolanan bir resmi görüntüleme

- Gelişmiş Meta dosyası kopyalarını oluşturma

- Gelişmiş Meta dosyasındaki tek tek kayıtları listeleme, düzenleme veya kopyalama

- Gelişmiş-Meta dosyası başlığından meta dosyası içeriklerinin isteğe bağlı bir açıklamasını alın

- Gelişmiş-Meta dosyası üstbilgisinin bir kopyasını alın

- Gelişmiş Meta dosyası ikili kopyasını alma

- İsteğe bağlı Paletteki renkleri listeleme

- Gelişmiş biçimdeki bir meta dosyası Windows-biçim meta dosyasına dönüştürme

Uygulama artık gelişmiş meta dosyası tanıtıcısına ihtiyaç duymuyorsa, Win32 `DeleteEnhMetaFile` işlevini çağırarak tanıtıcıyı serbest bırakmalıdır.

##  <a name="cmetafiledc"></a>CMetaFileDC:: CMetaFileDC

İki adımda `CMetaFileDC` bir nesne oluşturun.

```
CMetaFileDC();
```

### <a name="remarks"></a>Açıklamalar

İlk olarak `CMetaFileDC`, Windows meta dosyası `Create`cihaz bağlamını oluşturan `CMetaFileDC` ve bunu nesnesine bağlayan çağrısı yapın.

##  <a name="create"></a>CMetaFileDC:: Create

İki adımda `CMetaFileDC` bir nesne oluşturun.

```
BOOL Create(LPCTSTR lpszFilename = NULL);
```

### <a name="parameters"></a>Parametreler

*lpszFilename*<br/>
Null ile sonlandırılmış bir karakter dizesini işaret eder. Oluşturulacak meta dosyanın dosya adını belirtir. *LPSZFILENAME* null ise, yeni bir bellek içi meta dosyası oluşturulur.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışında bir değer, aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

İlk olarak, oluşturucuyu `CMetaFileDC`çağırın, sonra Windows meta dosyası cihaz bağlamını oluşturan `CMetaFileDC` ve bunu nesnesine ekleyen çağırın `Create`.

##  <a name="createenhanced"></a>CMetaFileDC:: CreateEnhanced

Gelişmiş biçimdeki meta dosya için bir cihaz bağlamı oluşturur.

```
BOOL CreateEnhanced(
    CDC* pDCRef,
    LPCTSTR lpszFileName,
    LPCRECT lpBounds,
    LPCTSTR lpszDescription);
```

### <a name="parameters"></a>Parametreler

*pDCRef*<br/>
Gelişmiş Meta dosyası için bir başvuru cihazı tanımlar.

*lpszFileName*<br/>
Null ile sonlandırılmış bir karakter dizesini işaret eder. Oluşturulacak gelişmiş meta dosyası için dosya adını belirtir. Bu parametre null ise, gelişmiş meta dosyası bellek tabanlıdır ve nesne yok edildiğinde ya da Win32 `DeleteEnhMetaFile` işlevi çağrıldığında kaybolur.

*Lpsınır*<br/>
Bir [Rect](/windows/win32/api/windef/ns-windef-rect) veri yapısına veya bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesine işaret eder ve bu da, gelişmiş meta dosyasında depolanacak olan resmin himetrik birimlerindeki (.01-milimetre ölçer artışlarla) boyutlarını belirtir.

*lpszDescription*<br/>
Resmi oluşturan uygulamanın adını ve resmin başlığını belirten sıfır ile sonlandırılmış bir dizeye işaret eder.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, geliştirilmiş meta dosyası için bir cihaz bağlamı tutamacı; Aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Bu DC, cihazdan bağımsız bir resim depolamak için kullanılabilir.

Windows, bir resmin başlangıçta göründüğü cihazın çözünürlüğünü ve birimlerini kaydetmek için *pDCRef* parametresi tarafından tanımlanan başvuru cihazını kullanır. *PDCRef* parametresi null ise, başvuru için geçerli görüntüleme cihazını kullanır.

`RECT` *Lpsınır* parametresi tarafından işaret edilen veri yapısının sol ve üst üyeleri sırasıyla sağ ve alt üyelerden daha küçük olmalıdır. Dikdörtgenin kenarları üzerindeki noktaları resme dahil edilir. *Lpsınır* null ise, grafik cihaz ARABIRIMI (GDI), uygulama tarafından çizilen resmi kapsayan en küçük dikdörtgenin boyutlarını hesaplar. Mümkün olduğunda, *Lpsınır* parametresi sağlanmalıdır.

*LpszDescription* parametresi tarafından işaret edilen dize, uygulama adı ve resim adı arasında bir null karakter içermeli ve iki null karakterle sonlanmalıdır — Örneğin, "xyz grafik Editor\0Bald Eagle\0\0," burada \ 0 şunu temsil eder null karakter. *LPSZDESCRIPTION* null ise, gelişmiş-meta dosyası üstbilgisinde karşılık gelen bir giriş yoktur.

Uygulamalar, bir grafik resmini gelişmiş bir meta dosyasında depolamak için bu işlev tarafından oluşturulan DC 'yi kullanır. Bu DC 'yi tanımlayan tanıtıcı herhangi bir GDI işlevine geçirilebilir.

Bir uygulama gelişmiş bir meta dosyasına bir resim depoladıktan sonra, `CDC::PlayMetaFile` işlevi çağırarak herhangi bir çıkış cihazında resmi görüntüleyebilir. Windows, resmi görüntülerken, *Lpsınır* parametresi tarafından işaret edilen dikdörtgeni ve resmi konumlandırmak ve ölçeklendirmek için başvuru cihazından çözüm verilerini kullanır. Bu işlev tarafından döndürülen cihaz bağlamı, yeni bir DC ile ilişkili aynı varsayılan öznitelikleri içeriyor.

Uygulamalar, gelişmiş bir meta `GetWinMetaFileBits` dosyası eski Windows meta dosyası biçimine dönüştürmek için Win32 işlevini kullanmalıdır.

Gelişmiş Meta dosyası için dosya adının ' i kullanması gerekir. EMF uzantısı.

## <a name="see-also"></a>Ayrıca bkz.

[CDC Sınıfı](../../mfc/reference/cdc-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
