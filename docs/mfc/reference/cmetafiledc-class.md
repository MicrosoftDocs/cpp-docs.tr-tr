---
title: "CMetaFileDC sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMetaFileDC
- AFXEXT/CMetaFileDC
- AFXEXT/CMetaFileDC::CMetaFileDC
- AFXEXT/CMetaFileDC::Close
- AFXEXT/CMetaFileDC::CloseEnhanced
- AFXEXT/CMetaFileDC::Create
- AFXEXT/CMetaFileDC::CreateEnhanced
dev_langs:
- C++
helpviewer_keywords:
- CMetaFileDC [MFC], CMetaFileDC
- CMetaFileDC [MFC], Close
- CMetaFileDC [MFC], CloseEnhanced
- CMetaFileDC [MFC], Create
- CMetaFileDC [MFC], CreateEnhanced
ms.assetid: ffce60fa-4181-4d46-9832-25e46fad4db4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8bb903bb38194be5b6a72f27ed683e965d7605b4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cmetafiledc-class"></a>CMetaFileDC sınıfı
İstenen görüntü veya metin oluşturmak için oynatabilirsiniz grafik cihaz arabirimi (GDI) komutları dizisini içeren bir Windows Meta dosyası uygular.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMetaFileDC : public CDC  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMetaFileDC::CMetaFileDC](#cmetafiledc)|Oluşturan bir `CMetaFileDC` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMetaFileDC::Close](#close)|Cihaz bağlamı kapatır ve meta dosyası tanıtıcı oluşturur.|  
|[CMetaFileDC::CloseEnhanced](#closeenhanced)|Geliştirilmiş Meta dosyası cihaz bağlamı kapatır ve geliştirilmiş meta dosyası tanıtıcı oluşturur.|  
|[CMetaFileDC::Create](#create)|Windows Meta dosyası cihaz bağlamı oluşturur ve ona ekler `CMetaFileDC` nesnesi.|  
|[CMetaFileDC::CreateEnhanced](#createenhanced)|Gelişmiş biçim meta dosyası için bir meta dosyası cihaz bağlamı oluşturur.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir Windows Meta dosyası uygulamak için önce oluşturmanız bir `CMetaFileDC` nesnesi. Çağırma `CMetaFileDC` oluşturucusu,'ı çağırın [oluşturma](#create) Windows Meta dosyası cihaz bağlamı oluşturur ve ona ekler üye işlevi `CMetaFileDC` nesnesi.  
  
 Sonraki Gönder `CMetaFileDC` bir dizi nesnesi `CDC` düşündüğünüz GDI komutları yeniden yürütme için. Çıkış, gibi oluşturduğunuz GDI komutları `MoveTo` ve `LineTo`, kullanılabilir.  
  
 İstenen komutların meta gönderdikten sonra arama **Kapat** meta dosyası cihaz bağlamları kapatır ve meta dosyası işleyici döner üye işlevi. Ardından elden `CMetaFileDC` nesnesi.  
  
 [CDC::PlayMetaFile](../../mfc/reference/cdc-class.md#playmetafile) meta dosyası tutamacı meta dosyası tekrar tekrar yürütmek için daha sonra kullanabilirsiniz. Meta dosyası ayrıca Windows işlevleri tarafından gibi yönetilebilir [CopyMetaFile](http://msdn.microsoft.com/library/windows/desktop/dd183480), disk için bir meta dosyası kopyalar.  
  
 Meta dosyası artık gerekli olmadığında ile bellekten silmek [DeleteMetaFile](http://msdn.microsoft.com/library/windows/desktop/dd183537) Windows işlevi.  
  
 Ayrıca uygulayabilirsiniz `CMetaFileDC` ele alabilir böylece hem de çıkış çağrıları ve öznitelik GDI çağrıları gibi nesne `GetTextExtent`. Bu tür bir meta dosyası daha esnektir ve daha sık çıkış ve öznitelik aramaları karışımını oluşur genel GDI kodu kolayca yeniden kullanabilirsiniz. `CMetaFileDC` Sınıfının devraldığı iki cihaz bağlamları `m_hDC` ve `m_hAttribDC`, gelen `CDC`. `m_hDC` Cihaz bağlamı tüm işler [CDC](../../mfc/reference/cdc-class.md) GDI çıktı çağrıları ve `m_hAttribDC` cihaz bağlamı tüm işler `CDC` GDI öznitelik aramaları. Normalde, bu iki cihaz bağlamları aynı cihaza bakın. Durumunda `CMetaFileDC`, DC özniteliği kümesine **NULL** varsayılan olarak.  
  
 Ekran, yazıcı veya aygıt bir meta dosyası dışında noktalarını'ı çağırın ikinci bir cihaz bağlamı oluşturmak `SetAttribDC` yeni cihaz bağlamıyla ilişkilendirilecek üye işlevi `m_hAttribDC`. GDI çağrıları bilgileri için şimdi yönlendirileceği yeni `m_hAttribDC`. Çıktı GDI çağrıları için yazılacak `m_hDC`, meta dosyası temsil eder.  
  
 Daha fazla bilgi için `CMetaFileDC`, bkz: [cihaz bağlamları](../../mfc/device-contexts.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CDC](../../mfc/reference/cdc-class.md)  
  
 `CMetaFileDC`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxext.h  
  
##  <a name="close"></a>CMetaFileDC::Close  
 Meta dosyası cihaz bağlamı kapatır ve meta dosyası kullanarak yürütmek için kullanılan bir Windows Meta dosyası tanıtıcı oluşturur [CDC::PlayMetaFile](../../mfc/reference/cdc-class.md#playmetafile) üye işlevi.  
  
```  
HMETAFILE Close();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli bir **HMETAFILE** işlevi başarılıysa ise **NULL**.  
  
### <a name="remarks"></a>Açıklamalar  
 Windows Meta dosyası tanıtıcı Windows işlevlerle meta dosyası gibi işlemek için de kullanılabilir [CopyMetaFile](http://msdn.microsoft.com/library/windows/desktop/dd183480).  
  
 Windows çağırarak kullandıktan sonra meta dosyası silmek [DeleteMetaFile](http://msdn.microsoft.com/library/windows/desktop/dd183537) işlevi.  
  
##  <a name="closeenhanced"></a>CMetaFileDC::CloseEnhanced  
 Geliştirilmiş Meta dosyası cihaz bağlamı kapatır ve Gelişmiş biçim meta dosyası tanımlayan bir işleyici döner.  
  
```  
HENHMETAFILE CloseEnhanced();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir Gelişmiş Meta dosyası, başarılı olursa tanıtıcısı; Aksi takdirde **NULL**.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir uygulama, aşağıdaki görevleri gerçekleştirmek için bu işlev tarafından döndürülen geliştirilmiş meta dosyası tanıtıcısıyla kullanabilirsiniz:  
  
-   Bir Gelişmiş Meta dosyası içinde depolanan resim görüntüleme  
  
-   Geliştirilmiş Meta dosyası kopyalarını oluşturun  
  
-   Listeleme, düzenlemek veya Gelişmiş Meta dosyası içinde ayrı ayrı kayıtları kopyalama  
  
-   Geliştirilmiş Meta dosyası başlığından isteğe bağlı bir açıklama meta dosyası içeriği alma  
  
-   Geliştirilmiş Meta dosyası üstbilgisi bir kopyasını alma  
  
-   Geliştirilmiş Meta dosyası ikili bir kopyasını alma  
  
-   İsteğe bağlı palet renkleri listeleme  
  
-   Gelişmiş biçim meta dosyası bir Windows biçimli meta dosyası Dönüştür  
  
 Uygulama artık gelişmiş meta dosyası tanıtıcı gerektiğinde, Win32 çağırarak tanıtıcı serbest **DeleteEnhMetaFile** işlevi.  
  
##  <a name="cmetafiledc"></a>CMetaFileDC::CMetaFileDC  
 Oluşturmak bir `CMetaFileDC` iki adımda nesne.  
  
```  
CMetaFileDC();
```  
  
### <a name="remarks"></a>Açıklamalar  
 İlk olarak, arama `CMetaFileDC`, ardından çağıran **oluşturma**, hangi Windows Meta dosyası cihaz bağlamı oluşturur ve ona ekler `CMetaFileDC` nesne.  
  
##  <a name="create"></a>CMetaFileDC::Create  
 Oluşturmak bir `CMetaFileDC` iki adımda nesne.  
  
```  
BOOL Create(LPCTSTR lpszFilename = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpszFilename*  
 Bir null olarak sonlandırılan bir karakter dizesi noktalarına. Dosya oluşturmak için meta dosyası adını belirtir. Varsa *lpszFilename* olan **NULL**, yeni bir bellek içi meta dosyası oluşturulur.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılı olursa sıfır dışında bir değer, aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk olarak, Oluşturucusu çağrısı `CMetaFileDC`,'ı çağırın **oluşturma**, hangi Windows Meta dosyası cihaz bağlamı oluşturur ve ona ekler `CMetaFileDC` nesnesi.  
  
##  <a name="createenhanced"></a>CMetaFileDC::CreateEnhanced  
 Gelişmiş biçim meta dosyası için bir cihaz bağlamı oluşturur.  
  
```  
BOOL CreateEnhanced(
    CDC* pDCRef,  
    LPCTSTR lpszFileName,  
    LPCRECT lpBounds,  
    LPCTSTR lpszDescription);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDCRef`  
 Geliştirilmiş Meta dosyası için bir başvuru cihaz tanımlar.  
  
 `lpszFileName`  
 Bir null olarak sonlandırılan bir karakter dizesi noktalarına. Oluşturulacak geliştirilmiş meta dosyası için dosya adını belirtir. Bu parametre ise **NULL**, Gelişmiş Meta dosyası bağlı olarak bellek ve içeriğinin veya nesne yok zaman kayıp olduğundan Win32 **DeleteEnhMetaFile** işlevi çağrılır.  
  
 `lpBounds`  
 İşaret eden bir [RECT](../../mfc/reference/rect-structure1.md) veri yapısı veya [CRect](../../atl-mfc-shared/reference/crect-class.md) boyutlar belirtir nesne **HIMETRIC** depolanmasına (.01 milimetre artışlarla) resmin birimleri Geliştirilmiş Meta dosyası.  
  
 `lpszDescription`  
 Noktaları sıfır sonlandırılan dizeye resmi olarak resmin başlık oluşturulan uygulamanın adını belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geliştirilmiş Meta dosyası, başarılı olursa cihaz bağlamı tanıtıcısı; Aksi takdirde **NULL**.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu DC aygıttan bağımsız resim depolamak için kullanılabilir.  
  
 Windows tarafından tanımlanan başvuru cihaz kullanan `pDCRef` çözümleme ve birimleri resim ilk olarak görünen cihaz kaydetmek için parametre. Varsa `pDCRef` parametresi **NULL**, geçerli görüntüleme cihazı için başvuru kullanır.  
  
 Sol ve üst üyelerinin `RECT` tarafından için veri yapısı işaret `lpBounds` parametresi sağ ve alt üyeleri küçük olmalıdır sırasıyla. Dikdörtgen kenarları boyunca noktaları resimde dahil edilir. Varsa `lpBounds` olan **NULL**, uygulama tarafından çizilmiş resmi içine dikdörtgenin en küçük boyut grafik cihaz arabirimi (GDI) hesaplar. `lpBounds` Parametresi sağlanan mümkün olduğunda.  
  
 Tarafından için dize işaret `lpszDescription` parametresi uygulama adı ve resim adı arasında bir null karakter içermeli ve iki null karakterlerle bitmesi — Örneğin, "XYZ grafik Editor\0Bald null \0 temsil ettiği Eagle\0\0," karakter. Varsa `lpszDescription` olan **NULL**, geliştirilmiş meta dosyası üstbilgisinde karşılık gelen bir girişi yok.  
  
 Uygulamalar bu işlev tarafından oluşturulan DC bir grafik resmi bir Gelişmiş Meta dosyası depolamak için kullanın. Bu DC tanımlayan tanıtıcı herhangi GDI işleve geçirilebilir.  
  
 Uygulamanın resim bir Gelişmiş Meta dosyası içinde depolar. sonra onu resmi herhangi bir çıktı cihazda çağırarak görüntüleyebilirsiniz `CDC::PlayMetaFile` işlevi. Resim görüntülerken, Windows'un gösterdiği dikdörtgen kullandığı `lpBounds` parametre ve konumlandırmak ve resim ölçeklendirmek için başvuru aygıttan çözümleme veri. Bu işlev tarafından döndürülen cihaz bağlamı herhangi yeni bir DC ile ilişkili aynı varsayılan öznitelikleri içerir.  
  
 Win32 uygulamaları kullanmalıdır **GetWinMetaFileBits** bir Gelişmiş Meta dosyası eski Windows Meta dosyası biçimine dönüştürmek için işlevi.  
  
 Geliştirilmiş Meta dosyası için dosya adını kullanmanız gerekir. EMF uzantısı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CDC sınıfı](../../mfc/reference/cdc-class.md)   
 [Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)



