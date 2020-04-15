---
title: CMetaFileDC Sınıfı
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
ms.openlocfilehash: 0919dacfd758df39064c5381690e9e23a029fcd1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369957"
---
# <a name="cmetafiledc-class"></a>CMetaFileDC Sınıfı

İstenilen bir resim veya metin oluşturmak için yeniden oynatabileceğiniz bir grafik aygıtı arabirimi (GDI) komutları içeren bir Windows metadosyası uygular.

## <a name="syntax"></a>Sözdizimi

```
class CMetaFileDC : public CDC
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CMetaFileDC::CMetaFileDC](#cmetafiledc)|Bir `CMetaFileDC` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMetaFileDC::Kapat](#close)|Aygıt bağlamını kapatır ve bir metadosya tutamacı oluşturur.|
|[CMetaFileDC::CloseEnhanced](#closeenhanced)|Gelişmiş metadosya aygıt bağlamı kapatır ve gelişmiş bir metadosya tutamacı oluşturur.|
|[CMetaFileDC::Oluştur](#create)|Windows metafile aygıt bağlamını oluşturur ve `CMetaFileDC` nesneye bağlar.|
|[CMetaFileDC::CreateEnhanced](#createenhanced)|Gelişmiş biçimli bir metadosya için metadosya aygıt bağlamı oluşturur.|

## <a name="remarks"></a>Açıklamalar

Bir Windows metadosyası uygulamak için `CMetaFileDC` önce bir nesne oluşturun. Oluşturucuyu `CMetaFileDC` çağırın, [Create](#create) ardından Windows metadosyası aygıt bağlamı oluşturan ve `CMetaFileDC` nesneye iliştiren Üye Oluştur işlevini çağırın.

Ardından nesneye `CMetaFileDC` yeniden oynatmasını istediğiniz CDC GDI komutlarının sırasını gönderin. Yalnızca çıktı oluşturan GDI komutları `MoveTo` kullanılabilir. `LineTo`

Metadosyaya istenen komutları gönderdikten sonra, `Close` metadosya aygıt bağlamlarını kapatan ve metadosya tutamacıdöndüran üye işlevi arayın. Sonra nesneyi `CMetaFileDC` atın.

[CDC::PlayMetaFile](../../mfc/reference/cdc-class.md#playmetafile) daha sonra metadosyayı tekrar tekrar çalmak için metadosya tutamacını kullanabilir. Metadosya, metadosyayı diske kopyalayan [CopyMetaFile](/windows/win32/api/wingdi/nf-wingdi-copymetafilew)gibi Windows işlevleri tarafından da işlenebilir.

Metadosyaya artık gerek kalmadığında, [DeleteMetaFile](/windows/win32/api/wingdi/nf-wingdi-deletemetafile) Windows işlevi ile bellekten silin.

Nesneyi, `CMetaFileDC` hem çıktı çağrılarını işleyebilir hem de GDI çağrıları `GetTextExtent`gibi öznitelik edebilsin diye de uygulayabilirsiniz. Böyle bir metadosya daha esnektir ve genellikle çıktı ve öznitelik çağrılarının bir karışımından oluşan genel GDI kodunu daha kolay yeniden kullanabilir. Sınıf, `CMetaFileDC` CDC'den iki `m_hDC` aygıt `m_hAttribDC`bağlamını ve cdc'yi devralır. Aygıt `m_hDC` bağlamı tüm [CDC](../../mfc/reference/cdc-class.md) GDI çıkış `m_hAttribDC` çağrılarını işler ve aygıt bağlamı tüm CDC GDI öznitelik çağrılarını işler. Normalde, bu iki aygıt bağlamı aynı aygıta başvurur. Durumunda `CMetaFileDC`, öznitelik DC varsayılan olarak NULL olarak ayarlanır.

Meta dosya dışındaki ekrana, yazıcıya veya aygıta işaret eden ikinci bir `SetAttribDC` aygıt bağlamı oluşturun ve `m_hAttribDC`ardından yeni aygıt bağlamını ' yla ilişkilendirmek için üye işlevi arayın. Bilgi için GDI çağrıları şimdi yeni `m_hAttribDC`yönlendirilecektir . Çıktı GDI çağrıları `m_hDC`, metadosyayı temsil eden gider.

Daha fazla `CMetaFileDC`bilgi için [Bkz. Aygıt Bağlamları.](../../mfc/device-contexts.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[CDC](../../mfc/reference/cdc-class.md)

`CMetaFileDC`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxext.h

## <a name="cmetafiledcclose"></a><a name="close"></a>CMetaFileDC::Kapat

Metafile aygıt bağlamını kapatır ve [CDC::PlayMetaFile](../../mfc/reference/cdc-class.md#playmetafile) üye işlevini kullanarak metadosyayı oynatmak için kullanılabilecek bir Windows metadosya tutamacı oluşturur.

```
HMETAFILE Close();
```

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa geçerli bir HMETAFILE; aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Windows metadosya tutamacı, [metadosyayı CopyMetaFile](/windows/win32/api/wingdi/nf-wingdi-copymetafilew)gibi Windows işlevleriyle işlemek için de kullanılabilir.

Windows [DeleteMetaFile](/windows/win32/api/wingdi/nf-wingdi-deletemetafile) işlevini arayarak metadosyayı kullanından sonra silin.

## <a name="cmetafiledccloseenhanced"></a><a name="closeenhanced"></a>CMetaFileDC::CloseEnhanced

Gelişmiş metadosya aygıt bağlamını kapatır ve gelişmiş biçimli bir metadosyayı tanımlayan bir tanıtıcı döndürür.

```
HENHMETAFILE CloseEnhanced();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, gelişmiş bir metadosyanın tutamacı; aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Bir uygulama, aşağıdaki görevleri gerçekleştirmek için bu işlev tarafından döndürülen gelişmiş metadosya tutamacını kullanabilir:

- Gelişmiş bir metadosyada depolanan bir resmi görüntüleme

- Geliştirilmiş metadosyanın kopyalarını oluşturma

- Gelişmiş metadosyadaki kayıtları tek tek kopyalama, kopyalama veya kopyalama

- Gelişmiş metadosya üstbilgisinden metadosya içeriğinin isteğe bağlı açıklamasını alma

- Geliştirilmiş metadosya üstbilgisinin bir kopyasını alma

- Geliştirilmiş metadosyanın ikili kopyasını alma

- İsteğe bağlı paletteki renkleri sayısala

- Gelişmiş biçimli metadosyayı Windows biçimli metadosyaya dönüştürme

Uygulama artık gelişmiş metadosya tutamacına ihtiyaç dakalolmadığında, Win32 `DeleteEnhMetaFile` işlevini arayarak tutamacı serbest bırakmalıdır.

## <a name="cmetafiledccmetafiledc"></a><a name="cmetafiledc"></a>CMetaFileDC::CMetaFileDC

Bir `CMetaFileDC` nesneyi iki adımda oluştur.

```
CMetaFileDC();
```

### <a name="remarks"></a>Açıklamalar

İlk olarak, Windows `Create`metafile aygıt bağlamını oluşturan ve `CMetaFileDC` nesneye iliştiren `CMetaFileDC`çağrı , sonra çağırın.

## <a name="cmetafiledccreate"></a><a name="create"></a>CMetaFileDC::Oluştur

Bir `CMetaFileDC` nesneyi iki adımda oluştur.

```
BOOL Create(LPCTSTR lpszFilename = NULL);
```

### <a name="parameters"></a>Parametreler

*lpszDosya adı*<br/>
Null-sonlandırılan karakter dizesini işaret edin. Oluşturmak için metadosyanın dosya adını belirtir. *lpszFilename* NULL ise, yeni bir bellek içi metadosya oluşturulur.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışında bir değer, aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

İlk olarak, Windows `CMetaFileDC`metafile `Create`aygıt bağlamını oluşturan ve `CMetaFileDC` nesneye iliştiren oluşturucuyu , sonra çağırın.

## <a name="cmetafiledccreateenhanced"></a><a name="createenhanced"></a>CMetaFileDC::CreateEnhanced

Gelişmiş biçimli bir metadosya için aygıt bağlamı oluşturur.

```
BOOL CreateEnhanced(
    CDC* pDCRef,
    LPCTSTR lpszFileName,
    LPCRECT lpBounds,
    LPCTSTR lpszDescription);
```

### <a name="parameters"></a>Parametreler

*pDCRef*<br/>
Geliştirilmiş metadosya için bir başvuru aygıtı tanımlar.

*lpszFileName*<br/>
Null-sonlandırılan karakter dizesini işaret edin. Oluşturulacak gelişmiş metadosya için dosya adını belirtir. Bu parametre NULL ise, geliştirilmiş metadosya bellek tabanlıdır ve nesne yok edildiğinde veya `DeleteEnhMetaFile` Win32 işlevi çağrıldığında içeriği kaybolur.

*lpBounds*<br/>
Geliştirilmiş metadosyada depolanacak resmin HIMETRIC birimlerindeki (0,01 milimetrelik artışlarla) boyutları belirten bir [RECT](/windows/win32/api/windef/ns-windef-rect) veri yapısına veya [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesine işaret eder.

*lpszAçıklama*<br/>
Resmi oluşturan uygulamanın adını ve resmin başlığını belirten sıfır sonlandırılmış dizeyi işaret eder.

### <a name="return-value"></a>Dönüş Değeri

Gelişmiş metadosya için aygıt bağlamının bir tutamacı, başarılı ise; aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Bu DC, aygıtdan bağımsız bir resmi depolamak için kullanılabilir.

Windows, resmin ilk kez göründüğü aygıtın çözünürlüğünü ve birimlerini kaydetmek için *pDCRef* parametresi tarafından tanımlanan başvuru aygıtını kullanır. *pDCRef* parametresi NULL ise, geçerli görüntü aygıtını başvuru için kullanır.

*LpBounds* parametresi `RECT` tarafından işaret edilen veri yapısının sol ve üst üyeleri sırasıyla sağ ve alt üyelerden daha küçük olmalıdır. Dikdörtgenin kenarlarındaki noktalar resimde yer alıyor. *lpBounds* NULL ise, grafik aygıtı arabirimi (GDI) uygulama tarafından çizilen resmi içine alabilirsiniz en küçük dikdörtgenin boyutlarını bilgilendiriyor. *LPBounds* parametresi mümkün si verilmelidir.

*lpszDescription* parametresi tarafından işaret edilen dize, uygulama adı ile resim adı arasında null bir karakter içermelidir ve \0'ın null karakterini temsil ettiği "XYZ Graphics Editor\0\0\0" gibi iki null karakterle sonlandırmalıdır. *lpszDescription* NULL ise, gelişmiş metadosya üstbilgisinde karşılık gelen bir giriş yoktur.

Uygulamalar, grafik resmini gelişmiş bir metadosyada depolamak için bu işlevtarafından oluşturulan DC'yi kullanır. Bu DC'yi tanımlayan tutamak herhangi bir GDI işlevine aktarılabilir.

Bir uygulama bir resmi gelişmiş bir metadosyada depoladıktan sonra, `CDC::PlayMetaFile` işlevi arayarak resmi herhangi bir çıktı aygıtında görüntüleyebilir. Resmi görüntülerken, Windows *lpBounds* parametresi tarafından işaret edilen dikdörtgeni ve başvuru aygıtından resmi konumlandırmak ve ölçeklendirmek için çözünürlük verilerini kullanır. Bu işlev tarafından döndürülen aygıt bağlamı, herhangi bir yeni DC ile ilişkili aynı varsayılan öznitelikleri içerir.

Uygulamalar, gelişmiş bir metadosyayı eski Windows metadosyası biçimine dönüştürmek için Win32 `GetWinMetaFileBits` işlevini kullanmalıdır.

Geliştirilmiş metadosya için dosya adı kullanmalısınız. EMF uzantısı.

## <a name="see-also"></a>Ayrıca bkz.

[CDC Sınıfı](../../mfc/reference/cdc-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
