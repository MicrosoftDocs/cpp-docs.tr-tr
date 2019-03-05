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
ms.openlocfilehash: 95f54f50d7a87e9a2ad4689c14f3b7f8d42ff71e
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57276795"
---
# <a name="cmetafiledc-class"></a>CMetaFileDC sınıfı

İstediğiniz görüntüyü veya metni oluşturmanız için yeniden yürütebileceğiniz grafik cihaz arabirimi (GDI) komutları dizisini içeren bir Windows Meta dosyası uygular.

## <a name="syntax"></a>Sözdizimi

```
class CMetaFileDC : public CDC
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMetaFileDC::CMetaFileDC](#cmetafiledc)|Oluşturur bir `CMetaFileDC` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMetaFileDC::Close](#close)|Cihaz bağlamı kapatır ve bir meta dosyası tanıtıcı oluşturur.|
|[CMetaFileDC::CloseEnhanced](#closeenhanced)|Bir Gelişmiş Meta dosyası cihaz bağlamı kapatır ve Gelişmiş Meta dosyası tanıtıcı oluşturur.|
|[CMetaFileDC::Create](#create)|Windows Meta dosyası cihaz bağlamı oluşturur ve ona ekler `CMetaFileDC` nesne.|
|[CMetaFileDC::CreateEnhanced](#createenhanced)|Bir biçim Gelişmiş Meta dosyası için bir meta dosyası cihaz bağlamı oluşturur.|

## <a name="remarks"></a>Açıklamalar

Bir Windows Meta dosyası uygulamak için ilk oluşturmak bir `CMetaFileDC` nesne. Çağırma `CMetaFileDC` oluşturucusu, ardından çağırın [Oluştur](#create) üye işlevi, bir Windows Meta dosyası cihaz bağlamı oluşturur ve ona ekler `CMetaFileDC` nesne.

Sonraki Gönder `CMetaFileDC` düşündüğünüz CDC GDI komutları yeniden yürütme için bir dizi nesnesi. Çıkış, gibi oluşturan GDI komutları `MoveTo` ve `LineTo`, kullanılabilir.

Meta dosyası için istenen komutların gönderdikten sonra çağrı `Close` meta dosyası cihaz bağlamları kapatır ve bir meta dosyası tanıtıcı döndüren üye işlevi. Ardından elden `CMetaFileDC` nesne.

[CDC::PlayMetaFile](../../mfc/reference/cdc-class.md#playmetafile) ardından meta tanıtıcı meta tekrar tekrar oynatmak için kullanabilirsiniz. Meta dosyası ayrıca Windows işlevleri tarafından gibi yönetilebilir [CopyMetaFile](/windows/desktop/api/wingdi/nf-wingdi-copymetafilea), disk için bir meta dosyası kopyalar.

Meta dosyası artık gerekli olmadığında, bellek ile Sil [DeleteMetaFile](/windows/desktop/api/wingdi/nf-wingdi-deletemetafile) Windows işlevi.

Ayrıca uygulayabilirsiniz `CMetaFileDC` işleyebileceği böylece hem de çıkış çağrıları ve öznitelik GDI çağrıları gibi nesne `GetTextExtent`. Böyle bir meta dosyası daha esnektir ve daha fazla çıkış ve öznitelik aramaları bir karışımını genellikle oluşan genel GDI kod kolayca yeniden kullanabilirsiniz. `CMetaFileDC` Sınıfından devralan iki cihaz bağlamları `m_hDC` ve `m_hAttribDC`, CDC öğesinden. `m_hDC` Cihaz bağlamı tüm işler [CDC](../../mfc/reference/cdc-class.md) GDI çıkış çağrıları ve `m_hAttribDC` cihaz bağlamı tüm CDC GDI öznitelik aramaları işler. Normalde, bu iki cihaz bağlamları aynı cihaza bakın. Durumunda, `CMetaFileDC`, DC öznitelik varsayılan olarak NULL olarak ayarlanır.

Ekran, yazıcı veya dışındaki bir meta dosyası cihaz noktalarına sonra çağıran ikinci bir cihaz bağlamı `SetAttribDC` üye işlevi, yeni bir cihaz bağlamı ile ilişkilendirilecek `m_hAttribDC`. GDI çağrıları bilgi artık yönlendirilir yeni `m_hAttribDC`. Çıkış GDI çağrıları için yazılacak `m_hDC`, meta dosyası temsil eder.

Daha fazla bilgi için `CMetaFileDC`, bkz: [cihaz bağlamları](../../mfc/device-contexts.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CDC](../../mfc/reference/cdc-class.md)

`CMetaFileDC`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxext.h

##  <a name="close"></a>  CMetaFileDC::Close

Meta dosyası cihaz bağlamı kapatır ve meta dosyası kullanarak yürütmek için kullanılan bir Windows Meta dosyası tanıtıcı oluşturur [CDC::PlayMetaFile](../../mfc/reference/cdc-class.md#playmetafile) üye işlevi.

```
HMETAFILE Close();
```

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa geçerli bir HMETAFILE; bulunmazsa null değerini DÖNDÜRÜR.

### <a name="remarks"></a>Açıklamalar

Windows Meta dosyası tanıtıcı Windows işlevleri ile yazılmışsa gibi işlemek için de kullanılabilir [CopyMetaFile](/windows/desktop/api/wingdi/nf-wingdi-copymetafilea).

Windows çağırarak meta kullandıktan sonra silin [DeleteMetaFile](/windows/desktop/api/wingdi/nf-wingdi-deletemetafile) işlevi.

##  <a name="closeenhanced"></a>  CMetaFileDC::CloseEnhanced

Bir Gelişmiş Meta dosyası cihaz bağlamı kapatır ve bir biçim Gelişmiş Meta dosyası tanımlayan bir tanıtıcı döndürür.

```
HENHMETAFILE CloseEnhanced();
```

### <a name="return-value"></a>Dönüş Değeri

Bir Gelişmiş Meta dosyası, başarılı olursa tanıtıcısı; bulunmazsa null değerini DÖNDÜRÜR.

### <a name="remarks"></a>Açıklamalar

Bir uygulama, bu işlev tarafından döndürülen Gelişmiş Meta dosyası tanıtıcı, aşağıdaki görevleri gerçekleştirmek için kullanabilirsiniz:

- Bir Gelişmiş Meta dosyası içinde depolanan bir resmi görüntülemek

- Gelişmiş Meta dosyası kopyasını oluşturma

- Numaralandırma, düzenlemek veya Gelişmiş Meta dosyası içinde tek tek kayıtlar kopyalayın

- Gelişmiş Meta dosyası başlığından isteğe bağlı bir açıklama meta dosyası içeriği alma

- Gelişmiş Meta dosyası üstbilgisi bir kopyasını alma

- Gelişmiş Meta dosyası ikili bir kopyasını alma

- İsteğe bağlı palet renkleri listeleme

- Bir Windows biçim meta dosyası bir biçim Gelişmiş Meta dosyası Dönüştür

Uygulama artık gelişmiş meta dosyası tanıtıcı gerektiğinde, Win32 çağırarak tanıtıcıyı serbest `DeleteEnhMetaFile` işlevi.

##  <a name="cmetafiledc"></a>  CMetaFileDC::CMetaFileDC

Oluşturmak bir `CMetaFileDC` iki adımda nesne.

```
CMetaFileDC();
```

### <a name="remarks"></a>Açıklamalar

İlk olarak, çağrı `CMetaFileDC`, ardından çağırın `Create`, hangi Windows Meta dosyası cihaz bağlamı oluşturur ve ona ekler `CMetaFileDC` nesne.

##  <a name="create"></a>  CMetaFileDC::Create

Oluşturmak bir `CMetaFileDC` iki adımda nesne.

```
BOOL Create(LPCTSTR lpszFilename = NULL);
```

### <a name="parameters"></a>Parametreler

*lpszFilename*<br/>
Null ile sonlandırılmış dizeye işaret eder. Dosya meta dosyası oluşturmak için adını belirtir. Varsa *lpszFilename* NULL ise yeni bir bellek içi meta dosyası oluşturulur.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışında bir değer, aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

İlk olarak, oluşturucusunu `CMetaFileDC`, ardından çağırın `Create`, Windows Meta dosyası cihaz bağlamı oluşturur ve ona ekler `CMetaFileDC` nesne.

##  <a name="createenhanced"></a>  CMetaFileDC::CreateEnhanced

Bir biçim Gelişmiş Meta dosyası için bir cihaz bağlamı oluşturur.

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
Null ile sonlandırılmış dizeye işaret eder. Oluşturulacak Gelişmiş Meta dosyası için dosya adını belirtir. Bu parametre NULL ise, Gelişmiş Meta dosyası bellek tabanlı ve içeriğini nesnesi yok edildiğinde veya zaman kayıp olduğundan Win32 `DeleteEnhMetaFile` işlevi çağrılır.

*lpBounds*<br/>
İşaret eden bir [RECT](/windows/desktop/api/windef/ns-windef-tagrect) veri yapısı veya [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesini resmi (artışlarla başına.01 milimetre) HIMETRIC birimleri Gelişmiş Meta dosyası içinde depolanacak boyutlarını belirtir.

*lpszDescription*<br/>
Resmin başlığı yanı sıra resmi oluşturduğunuz uygulamayı adını belirten bir sıfır ile sonlandırılmış dize işaret eder.

### <a name="return-value"></a>Dönüş Değeri

Gelişmiş Meta dosyası, başarılı olursa cihaz bağlamı tanıtıcısı; bulunmazsa null değerini DÖNDÜRÜR.

### <a name="remarks"></a>Açıklamalar

Bu etki alanı Denetleyicisinin bir CİHAZDAN bağımsız resmi depolamak için kullanılabilir.

Windows tarafından tanımlanan başvuru cihazını kullanan *pDCRef* çözümleme ve birimleri resim başlangıçta görünen cihaz kaydetmek için parametre. Varsa *pDCRef* parametre NULL ise, başvurusunu geçerli görüntü cihazı kullanır.

Sol ve üst üyelerinin `RECT` veri yapısı tarafından işaret edilen *lpBounds* parametresi sağ ve alt üyelerin küçük olmalıdır sırasıyla. Dikdörtgenin kenarlarının noktaları resmi dahil edilir. Varsa *lpBounds* null, uygulama tarafından çizilen resmi içine en küçük dikdörtgenin boyutlarına grafik cihaz arabirimi (GDI) hesaplar. *LpBounds* mümkün olduğunda parametresi'nin belirtilmelidir.

Dize tarafından işaret edilen *lpszDescription* parametresi uygulama adı ve resim adı arasında bir null karakter içermeli ve iki null karakteri ile sonlandırmanız gerekir — Örneğin, "XYZ grafik Editor\0Bald Eagle\0\0, "nerede \0 null karakteri temsil eder. Varsa *lpszDescription* NULL ise Gelişmiş Meta dosyası üst bilgisinde karşılık gelen bir giriş yok.

Uygulamalar bu işlev tarafından oluşturulan DC bir Gelişmiş Meta dosyası içinde bir grafik resmini depolamak için kullanır. Bu DC tanımlayan tanıtıcı GDI fonksiyonlarla geçirilebilir.

Bir uygulama bir resim bir Gelişmiş Meta dosyası içinde depolar. sonra onu resmi herhangi bir çıktı cihazda çağırarak görüntüleyebilirsiniz `CDC::PlayMetaFile` işlevi. Resim görüntülerken, işaret ettiği dikdörtgen Windows kullanan *lpBounds* parametresi ve getirin ve resmi ölçeklendirmek için başvuru CİHAZDAN çözümleme verileri. Bu işlev tarafından döndürülen bir cihaz bağlamı ile yeni bir DC'ye ilişkili aynı varsayılan öznitelikleri içerir.

Win32 uygulamaları kullanmalıdır `GetWinMetaFileBits` bir Gelişmiş Meta dosyası eski Windows Meta dosyası biçimine dönüştürmek için işlevi.

Gelişmiş Meta dosyası için dosya adı kullanmanız gerekir. EMF uzantısı.

## <a name="see-also"></a>Ayrıca bkz.

[CDC Sınıfı](../../mfc/reference/cdc-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
