---
title: CBitmap sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CBitmap
- AFXWIN/CBitmap
- AFXWIN/CBitmap::CBitmap
- AFXWIN/CBitmap::CreateBitmap
- AFXWIN/CBitmap::CreateBitmapIndirect
- AFXWIN/CBitmap::CreateCompatibleBitmap
- AFXWIN/CBitmap::CreateDiscardableBitmap
- AFXWIN/CBitmap::FromHandle
- AFXWIN/CBitmap::GetBitmap
- AFXWIN/CBitmap::GetBitmapBits
- AFXWIN/CBitmap::GetBitmapDimension
- AFXWIN/CBitmap::LoadBitmap
- AFXWIN/CBitmap::LoadMappedBitmap
- AFXWIN/CBitmap::LoadOEMBitmap
- AFXWIN/CBitmap::SetBitmapBits
- AFXWIN/CBitmap::SetBitmapDimension
dev_langs:
- C++
helpviewer_keywords:
- CBitmap [MFC], CBitmap
- CBitmap [MFC], CreateBitmap
- CBitmap [MFC], CreateBitmapIndirect
- CBitmap [MFC], CreateCompatibleBitmap
- CBitmap [MFC], CreateDiscardableBitmap
- CBitmap [MFC], FromHandle
- CBitmap [MFC], GetBitmap
- CBitmap [MFC], GetBitmapBits
- CBitmap [MFC], GetBitmapDimension
- CBitmap [MFC], LoadBitmap
- CBitmap [MFC], LoadMappedBitmap
- CBitmap [MFC], LoadOEMBitmap
- CBitmap [MFC], SetBitmapBits
- CBitmap [MFC], SetBitmapDimension
ms.assetid: 3980616a-c59d-495a-86e6-62bd3889c84c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e5b931c7ad4b560ce247f78dcb126f9669bceb67
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33355869"
---
# <a name="cbitmap-class"></a>CBitmap sınıfı
Bir Windows grafik cihaz arabirimi (GDI) bit eşlem yalıtır ve bit eşlem işlemek için üye işlevleri sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CBitmap : public CGdiObject  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CBitmap::CBitmap](#cbitmap)|Oluşturan bir `CBitmap` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CBitmap::CreateBitmap](#createbitmap)|Belirtilen genişlik, yükseklik ve bit düzeni sahip bir aygıta bağımlı bellek bitmap nesnesiyle başlatır.|  
|[CBitmap::CreateBitmapIndirect](#createbitmapindirect)|Verilen bir bit eşlem genişlik, yükseklik ve (belirtilmişse) bit desen ile nesnesiyle başlatır bir **bit eşlem** yapısı.|  
|[CBitmap::CreateCompatibleBitmap](#createcompatiblebitmap)|Böylece belirtilen bir aygıt ile uyumlu bir bit eşlem nesnesiyle başlatır.|  
|[CBitmap::CreateDiscardableBitmap](#creatediscardablebitmap)|Belirtilen bir aygıt ile uyumlu olan discardable bir bit eşlem nesnesiyle başlatır.|  
|[CBitmap::FromHandle](#fromhandle)|Bir işaretçi döndüren bir `CBitmap` nesnesi tanıtıcı Windows verildiğinde `HBITMAP` bitmap.|  
|[CBitmap::GetBitmap](#getbitmap)|Doldurur bir **bit eşlem** bit eşlem hakkında bilgi içeren yapısı.|  
|[CBitmap::GetBitmapBits](#getbitmapbits)|Belirtilen bit eşlem BITS belirtilen arabelleğe kopyalar.|  
|[CBitmap::GetBitmapDimension](#getbitmapdimension)|Bit eşlem yüksekliğini ve genişliğini döndürür. Genişliği ve yüksekliği önceden ayarlanmış kabul edilir [SetBitmapDimension](#setbitmapdimension) üye işlevi.|  
|[CBitmap::LoadBitmap](#loadbitmap)|Bir adlandırılmış bit eşlem kaynak yüklenen uygulamanın yürütülebilir dosya ve bit eşlem nesnesine ekleme nesnesini başlatır.|  
|[CBitmap::LoadMappedBitmap](#loadmappedbitmap)|Bir bit eşlemi yükleyen ve geçerli sistem renkleri renkler eşlenir.|  
|[CBitmap::LoadOEMBitmap](#loadoembitmap)|Önceden tanımlanmış bir Windows bit eşlem yükleme ve bit eşlem nesnesine ekleme tarafından nesnesini başlatır.|  
|[CBitmap::SetBitmapBits](#setbitmapbits)|Bir bit eşlem BITS belirtilen bit değerine ayarlar.|  
|[CBitmap::SetBitmapDimension](#setbitmapdimension)|Genişlik ve yükseklik bir bit eşlem 0,1 milimetre birimlerindeki atar.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CBitmap::operator HBITMAP](#operator_hbitmap)|Bağlı Windows işleyici döner `CBitmap` nesnesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanılacak bir `CBitmap` nesne, nesne oluşturmak, başlatma üye işlevleri birine bir bit eşlem tanıtıcı ekleme ve nesnenin üye işlevlerini çağırın.  
  
 Grafik nesneleri gibi kullanma hakkında daha fazla bilgi için `CBitmap`, bkz: [grafik nesneleri](../../mfc/graphic-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CBitmap`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwin.h  
  
##  <a name="cbitmap"></a>  CBitmap::CBitmap  
 Oluşturan bir `CBitmap` nesnesi.  
  
```  
CBitmap();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Elde edilen nesnenin başlatma üye işlevleri biri ile başlatılması gerekir.  
  
##  <a name="createbitmap"></a>  CBitmap::CreateBitmap  
 Belirtilen genişlik, yükseklik ve bit düzeni sahip bir aygıta bağımlı bellek bit eşlem başlatır.  
  
```  
BOOL CreateBitmap(
    int nWidth,  
    int nHeight,  
    UINT nPlanes,  
    UINT nBitcount,  
    const void* lpBits);
```  
  
### <a name="parameters"></a>Parametreler  
 `nWidth`  
 Bit eşlem genişliğini (piksel cinsinden) belirtir.  
  
 `nHeight`  
 Bit eşlem (piksel cinsinden) yüksekliğini belirtir.  
  
 `nPlanes`  
 Renk düzlemi sayısı eşleminde belirtir.  
  
 `nBitcount`  
 Renk bit görüntü piksel sayısını belirtir.  
  
 `lpBits`  
 İlk bit eşlem bit değerleri içeren bir bayt dizisi noktalarına. Eğer öyleyse **NULL**, yeni bit eşlem sol başlatılmamış.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir renk bit eşlem için ya da `nPlanes` veya `nBitcount` parametresi 1 olarak ayarlanmalıdır. Bu parametrelerin her ikisi de 1 olarak ayarlanırsa `CreateBitmap` tek renkli bir bit eşlem oluşturur.  
  
 Bir bit eşlem görüntüleme cihazı için doğrudan seçilemez rağmen bunu bir "bellek cihaz bağlamı" geçerli bit eşlem olarak kullanarak seçilebilir [CDC::SelectObject](../../mfc/reference/cdc-class.md#selectobject) ve kullanaraktümuyumlucihazbağlamınakopyaladığınız[CDC::BitBlt](../../mfc/reference/cdc-class.md#bitblt) işlevi.  
  
 İle tamamladığınızda `CBitmap` tarafından oluşturulan nesne `CreateBitmap` işlev, önce cihaz bağlamı dışında bit eşlem'i seçin, ardından silin `CBitmap` nesnesi.  
  
 Daha fazla bilgi için açıklamasına bakın **bmBits** alanındaki **bit eşlem** yapısı. [Bit eşlem](../../mfc/reference/bitmap-structure.md) altında yapısı açıklanan [CBitmap::CreateBitmapIndirect](#createbitmapindirect) üye işlevi.  
  
##  <a name="createbitmapindirect"></a>  CBitmap::CreateBitmapIndirect  
 Genişlik, yükseklik ve gösterdiği yapısı verilen (belirtilmişse) bit düzeni sahip bir bit eşlem başlatır `lpBitmap`.  
  
```  
BOOL CreateBitmapIndirect(LPBITMAP lpBitmap);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpBitmap`  
 İşaret eden bir [bit eşlem](../../mfc/reference/bitmap-structure.md) bit eşlem hakkında bilgi içeren yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir bit eşlem görüntüleme cihazı için doğrudan seçilemez karşın, bir bellek cihaz bağlamı için geçerli bit eşlem olarak kullanarak seçilebilmesi [CDC::SelectObject](../../mfc/reference/cdc-class.md#selectobject) ve kullanaraktümuyumlucihazbağlamınakopyaladığınız[CDC::BitBlt](../../mfc/reference/cdc-class.md#bitblt) veya [CDC::StretchBlt](../../mfc/reference/cdc-class.md#stretchblt) işlevi. ( [CDC::PatBlt](../../mfc/reference/cdc-class.md#patblt) işlevi doğrudan görüntü cihaz bağlamı geçerli fırça bit eşlem kopyalayabilir.)  
  
 Varsa **bit eşlem** tarafından yapısı işaret için `lpBitmap` parametresi doldurulmuş kullanarak `GetObject` işlevi, bit eşlem BITS belirtilmedi ve bit eşlem başlatılmadı. Bit eşlem başlatmak için uygulamanın bir işlev gibi kullanabilir [CDC::BitBlt](../../mfc/reference/cdc-class.md#bitblt) veya [SetDIBits](http://msdn.microsoft.com/library/windows/desktop/dd162973) ilk parametresi tarafından tanımlanan bit eşlem BITS kopyalanacak `CGdiObject::GetObject` tarafından oluşturulan bit eşlem için `CreateBitmapIndirect`.  
  
 İle tamamladığınızda `CBitmap` ile oluşturulan nesne `CreateBitmapIndirect` işlev, önce cihaz bağlamı dışında bit eşlem'i seçin, ardından silin `CBitmap` nesnesi.  
  
##  <a name="createcompatiblebitmap"></a>  CBitmap::CreateCompatibleBitmap  
 Belirtilen aygıt ile uyumlu bir bit eşlem başlatır `pDC`.  
  
```  
BOOL CreateCompatibleBitmap(
    CDC* pDC,  
    int nWidth,  
    int nHeight);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDC`  
 Cihaz bağlamı belirtir.  
  
 `nWidth`  
 Bit eşlem genişliğini (piksel cinsinden) belirtir.  
  
 `nHeight`  
 Bit eşlem (piksel cinsinden) yüksekliğini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bit eşlem Renk düzlemi aynı sayıda veya belirtilen cihaz bağlamı aynı bit / piksel biçimi vardır. Geçerli bit eşlem tarafından belirtilen biriyle uyumlu olan herhangi bir bellek aygıt olarak seçilebilir `pDC`.  
  
 Varsa `pDC` bir bellek cihaz bağlamı döndürülen bit eşlem şu anda seçili bit eşlem dosyası ile aynı biçimi bu cihaz bağlamında sahiptir. "Bellek cihaz bağlamı" bir görüntü yüzeyini temsil eden bellek bloğudur. Uyumlu aygıt gerçek görüntü yüzeye kopyalamadan önce bellekte resimler hazırlamak için kullanılabilir.  
  
 Bellek cihaz bağlamı oluşturulduğunda GDI tek renkli stok bit eşlem için otomatik olarak seçer.  
  
 Bir renk bellek cihaz bağlamı rengini veya seçili bitmap sahip olduğundan, bit eşlem biçimi tarafından döndürülen `CreateCompatibleBitmap` işlevi değil her zaman aynı; ancak, bir nonmemory cihaz bağlamı için uyumlu bir bit eşlem biçimi her zaman içinde Aygıt biçimi.  
  
 İle tamamladığınızda `CBitmap` ile oluşturulan nesne `CreateCompatibleBitmap` işlev, önce cihaz bağlamı dışında bit eşlem'i seçin, ardından silin `CBitmap` nesnesi.  
  
##  <a name="creatediscardablebitmap"></a>  CBitmap::CreateDiscardableBitmap  
 Tarafından tanımlanan cihaz bağlamı ile uyumlu olan discardable bir bit eşlem başlatır `pDC`.  
  
```  
BOOL CreateDiscardableBitmap(
    CDC* pDC,  
    int nWidth,  
    int nHeight);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDC`  
 Bir cihaz bağlamı belirtir.  
  
 `nWidth`  
 Bit eşlem (BITS) genişliğini belirtir.  
  
 `nHeight`  
 Bit eşlem (BITS) yüksekliğini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bit eşlem Renk düzlemi aynı sayıda veya belirtilen cihaz bağlamı aynı bit / piksel biçimi vardır. Bir uygulama tarafından belirtilen bir ile uyumlu bir bellek aygıtı geçerli bit eşlem olarak bu bit eşlemi seçebilirsiniz `pDC`.  
  
 Windows, yalnızca bir uygulama onu görünen bağlamına seçilmemişse bu işlev tarafından oluşturulan bir bit eşlem atabilirsiniz. Seçili değilse ve onu seçmek uygulamayı daha sonra çalışır, Windows bit eşlem atar varsa [CDC::SelectObject](../../mfc/reference/cdc-class.md#selectobject) işlevi döndürecektir **NULL**.  
  
 İle tamamladığınızda `CBitmap` ile oluşturulan nesne `CreateDiscardableBitmap` işlev, önce cihaz bağlamı dışında bit eşlem'i seçin, ardından silin `CBitmap` nesnesi.  
  
##  <a name="fromhandle"></a>  CBitmap::FromHandle  
 Bir işaretçi döndüren bir `CBitmap` nesnesi tanıtıcı bir Windows GDI bit eşlem verildiğinde.  
  
```  
static CBitmap* PASCAL FromHandle(HBITMAP hBitmap);
```  
  
### <a name="parameters"></a>Parametreler  
 `hBitmap`  
 Bir Windows GDI bit eşlem belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi bir `CBitmap` nesne başarılı; Aksi takdirde **NULL**.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa bir `CBitmap` nesne zaten iliştirilmemiş tanıtıcıyı, geçici bir `CBitmap` nesnesi oluşturulur ve bağlı. Bu geçici `CBitmap` nesnesi, hangi tüm geçici grafiği zaman durdurulacağını sonraki açışınızda uygulama boşta kalma süresi, olay döngüde olana kadar nesneler silinir yalnızca geçerli. Bu bildiren başka bir şekilde geçici nesne yalnızca bir pencere ileti işleme sırasında geçerli olmasıdır.  
  
##  <a name="getbitmap"></a>  CBitmap::GetBitmap  
 Ekli bit eşlem resim özelliklerini alır.  
  
```  
int GetBitmap(BITMAP* pBitMap);
```  
  
### <a name="parameters"></a>Parametreler  
 `pBitMap`  
 İşaretçi bir [bit eşlem yapısı](../../mfc/reference/bitmap-structure.md) görüntü özelliklerini alacak yapısı. Bu parametre olmamalıdır `NULL`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getbitmapbits"></a>  CBitmap::GetBitmapBits  
 Ekli bit eşlem bit desenini belirtilen arabelleğe kopyalar.  
  
```  
DWORD GetBitmapBits(
    DWORD dwCount,  
    LPVOID lpBits) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `dwCount`  
 Arabelleğe kopyalanacak bayt sayısı.  
  
 `lpBits`  
 Bit eşlem alacak arabellek işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa arabelleğin kopyalanan bayt sayısı; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım [CBitmap::GetBitmap](#getbitmap) gerekli arabellek boyutunu belirlemek için.  
  
##  <a name="getbitmapdimension"></a>  CBitmap::GetBitmapDimension  
 Bit eşlem yüksekliğini ve genişliğini döndürür.  
  
```  
CSize GetBitmapDimension() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bit eşlem yüksekliğini ve genişliğini 0,1 milimetre birimler cinsinden ölçülür. Yükseklik olarak **cy** üyesi `CSize` nesne ve genişliği **cx** üyesi. Bit eşlem genişliği ve yüksekliği kullanarak ayarlanmamış ise `SetBitmapDimension`, dönüş değeri 0'dır.  
  
### <a name="remarks"></a>Açıklamalar  
 Yüksekliğini ve genişliğini kullanarak önceden ayarlanan varsayılır [SetBitmapDimension](#setbitmapdimension) üye işlevi.  
  
##  <a name="loadbitmap"></a>  CBitmap::LoadBitmap  
 Tarafından adlı bit eşlem kaynağı yükler `lpszResourceName` veya kimlik numarası ile tanımlanan `nIDResource` uygulamanın yürütülebilir dosya.  
  
```  
BOOL LoadBitmap(LPCTSTR lpszResourceName);  
BOOL LoadBitmap(UINT nIDResource);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszResourceName`  
 Bit eşlem kaynağın adını içeren null ile sonlandırılmış bir dize noktalarına.  
  
 `nIDResource`  
 Bit eşlem kaynağının kaynak kimliği numarasını belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Yüklenen bitmap bağlı `CBitmap` nesnesi.  
  
 Bit eşlem tarafından tanımladıysanız `lpszResourceName` yok veya bit eşlem'i yüklemek için yeterli bellek varsa, işlev 0 döndürür.  
  
 Kullanabileceğiniz [CGdiObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject) bit eşlem Sil işlevi yüklenen tarafından `LoadBitmap` işlevi, veya `CBitmap` yıkıcı nesne sizin için siler.  
  
> [!CAUTION]
>  Nesne silmeden önce bir cihaz bağlamına seçili olmadığından emin olun.  
  
 Aşağıdaki 3.1 ve sonraki Windows sürümleri için eklendi:  
  
 **OBM_UPARRROWIOBM_DNARROWIOBM_RGARROWIOBM_LFARROWI**  
  
 Bu bit eşlemler aygıt sürücülerini Windows sürümleri için de 3.0 ve öncesini bulunamadı. Bit eşlemler ve görünümlerini görüntüsünü tam listesi için Windows SDK'sı bakın.  
  
##  <a name="loadmappedbitmap"></a>  CBitmap::LoadMappedBitmap  
 Bir bit eşlem yük ve geçerli sistem renkleri renkleri eşlemek için bu üye işlevini çağırın.  
  
```  
BOOL LoadMappedBitmap(
    UINT nIDBitmap,  
    UINT nFlags = 0,  
    LPCOLORMAP lpColorMap = NULL,  
    int nMapSize = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 `nIDBitmap`  
 Bit eşlem kaynak kimliği.  
  
 `nFlags`  
 Bir bit eşlem için bir bayrak. Sıfır olabilir veya **CMB_MASKED**.  
  
 `lpColorMap`  
 Bir işaretçi bir **COLORMAP** bit eşlemler eşlemek için gereken renk bilgilerini içeren yapısı. Bu parametre ise **NULL**, varsayılan renk eşlemesi işlevi kullanır.  
  
 *nMapSize*  
 Tarafından için renk eşlemeleri sayısı işaret `lpColorMap`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, `LoadMappedBitmap` düğmesi metindeki yaygın olarak kullanılan renkleri eşler.  
  
 Eşlenmiş bir bit eşlem oluşturma hakkında daha fazla bilgi için bkz: Windows işlevi [CreateMappedBitmap](http://go.microsoft.com/fwlink/p/?linkid=230562) ve [COLORMAP](http://msdn.microsoft.com/library/windows/desktop/bb760448) Windows SDK'sındaki yapısı.  
  
##  <a name="loadoembitmap"></a>  CBitmap::LoadOEMBitmap  
 Windows tarafından kullanılan önceden tanımlanmış bir bit eşlem yükler.  
  
```  
BOOL LoadOEMBitmap(UINT nIDBitmap);
```  
  
### <a name="parameters"></a>Parametreler  
 `nIDBitmap`  
 Önceden tanımlanmış Windows bit eşlem kimliği sayısı. Olası değerler varsayılan olarak, WINDOWS aşağıda listelenmiştir. Y:  
  
|||  
|-|-|  
|**OBM_BTNCORNERS**|**OBM_OLD_RESTORE**|  
|**OBM_BTSIZE**|**OBM_OLD_RGARROW**|  
|**OBM_CHECK**|**OBM_OLD_UPARROW**|  
|**OBM_CHECKBOXES**|**OBM_OLD_ZOOM**|  
|**OBM_CLOSE**|**OBM_REDUCE**|  
|**OBM_COMBO**|**OBM_REDUCED**|  
|**OBM_DNARROW**|**OBM_RESTORE**|  
|**OBM_DNARROWD**|**OBM_RESTORED**|  
|**OBM_DNARROWI**|**OBM_RGARROW**|  
|**OBM_LFARROW**|**OBM_RGARROWD**|  
|**OBM_LFARROWD**|**OBM_RGARROWI**|  
|**OBM_LFARROWI**|**OBM_SIZE**|  
|**OBM_MNARROW**|**OBM_UPARROW**|  
|**OBM_OLD_CLOSE**|**OBM_UPARROWD**|  
|**OBM_OLD_DNARROW**|**OBM_UPARROW**|  
|**OBM_OLD_LFARROW**|**OBM_ZOOM**|  
|**OBM_OLD_REDUCE**|**OBM_ZOOMD**|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 İle başlayan adları bitmap **OBM_OLD** 3.0'den önceki Windows sürümleri tarafından kullanılan bit eşlemler temsil eder.  
  
 Unutmayın sabiti **OEMRESOURCE** WINDOWS eklemeden önce tanımlanmalıdır. Herhangi birini kullanmak için H **OBM_** sabitleri.  
  
##  <a name="operator_hbitmap"></a>  CBitmap::operator HBITMAP  
 Ekli Windows GDI işleyicisini almak için bu işleci kullanın `CBitmap` nesnesi.  
  
```  
operator HBITMAP() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı, Windows GDI nesnesi için bir tanıtıcı tarafından temsil edilen varsa `CBitmap` nesne; Aksi halde **NULL**.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işleç doğrudan kullanımını destekleyen bir atama işleci olan bir `HBITMAP` nesnesi.  
  
 Grafik nesneleri kullanma hakkında daha fazla bilgi için bkz: [grafik nesneleri](http://msdn.microsoft.com/library/windows/desktop/dd144962) Windows SDK.  
  
##  <a name="setbitmapbits"></a>  CBitmap::SetBitmapBits  
 Bir bit eşlem BITS tarafından verilen bit değerlerini ayarlar `lpBits`.  
  
```  
DWORD SetBitmapBits(
    DWORD dwCount,  
    const void* lpBits);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwCount`  
 Gösterdiği bayt sayısını belirtir `lpBits`.  
  
 `lpBits`  
 İşaret **bayt** kopyalanması için piksel değerlerini içeren bir dizi `CBitmap` nesnesi. Bit eşlem görüntüsünü doğru şekilde oluşturmak sırayla değerleri CBitmap örneği oluşturulduğunda, belirtilen yükseklik ve genişlik renk derinliği değerlere uyacak şekilde biçimlendirilmelidir. Daha fazla bilgi için bkz: [CBitmap::CreateBitmap](#createbitmap).  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bit eşlem BITS ayarlarken kullanılan bayt sayısı; 0 işlev başarısız olur.  
  
##  <a name="setbitmapdimension"></a>  CBitmap::SetBitmapDimension  
 Genişlik ve yükseklik bir bit eşlem 0,1 milimetre birimlerindeki atar.  
  
```  
CSize SetBitmapDimension(
    int nWidth,  
    int nHeight);
```  
  
### <a name="parameters"></a>Parametreler  
 `nWidth`  
 Bit eşlem (0,1 milimetre birimlerindeki) genişliğini belirtir.  
  
 `nHeight`  
 Bit eşlem (0,1 milimetre birimlerindeki) yüksekliğini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Önceki bit eşlem boyutları. Yükseklik konusu **cy** üye değişken `CSize` nesne ve genişlik **cx** üye değişkeni.  
  
### <a name="remarks"></a>Açıklamalar  
 GDI bir uygulama çağırdığında dışında döndürmek için bu değerleri kullanmaz [GetBitmapDimension](#getbitmapdimension) üye işlevi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek MDI](../../visual-cpp-samples.md)   
 [CGdiObject sınıfı](../../mfc/reference/cgdiobject-class.md)   
 [Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)

