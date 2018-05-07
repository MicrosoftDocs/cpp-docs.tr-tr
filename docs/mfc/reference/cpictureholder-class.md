---
title: CPictureHolder sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CPictureHolder
- AFXCTL/CPictureHolder
- AFXCTL/CPictureHolder::CPictureHolder
- AFXCTL/CPictureHolder::CreateEmpty
- AFXCTL/CPictureHolder::CreateFromBitmap
- AFXCTL/CPictureHolder::CreateFromIcon
- AFXCTL/CPictureHolder::CreateFromMetafile
- AFXCTL/CPictureHolder::GetDisplayString
- AFXCTL/CPictureHolder::GetPictureDispatch
- AFXCTL/CPictureHolder::GetType
- AFXCTL/CPictureHolder::Render
- AFXCTL/CPictureHolder::SetPictureDispatch
- AFXCTL/CPictureHolder::m_pPict
dev_langs:
- C++
helpviewer_keywords:
- CPictureHolder [MFC], CPictureHolder
- CPictureHolder [MFC], CreateEmpty
- CPictureHolder [MFC], CreateFromBitmap
- CPictureHolder [MFC], CreateFromIcon
- CPictureHolder [MFC], CreateFromMetafile
- CPictureHolder [MFC], GetDisplayString
- CPictureHolder [MFC], GetPictureDispatch
- CPictureHolder [MFC], GetType
- CPictureHolder [MFC], Render
- CPictureHolder [MFC], SetPictureDispatch
- CPictureHolder [MFC], m_pPict
ms.assetid: a4f59775-704a-41dd-b5bd-2e531c95127a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0c2ffbe685ac643116fa60d4f97d03781d1efc83
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="cpictureholder-class"></a>CPictureHolder sınıfı
Resim, denetiminde görüntüleme olanak tanır. bir resim özelliği uygular.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CPictureHolder  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CPictureHolder::CPictureHolder](#cpictureholder)|Oluşturan bir `CPictureHolder` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CPictureHolder::CreateEmpty](#createempty)|Boş bir oluşturur `CPictureHolder` nesnesi.|  
|[CPictureHolder::CreateFromBitmap](#createfrombitmap)|Oluşturur bir `CPictureHolder` bir bit eşlem nesnesinden.|  
|[CPictureHolder::CreateFromIcon](#createfromicon)|Oluşturur bir `CPictureHolder` simge nesnesinden.|  
|[CPictureHolder::CreateFromMetafile](#createfrommetafile)|Oluşturur bir `CPictureHolder` meta dosyası nesnesinden.|  
|[CPictureHolder::GetDisplayString](#getdisplaystring)|Bir denetim kapsayıcının özelliği tarayıcıda görüntülenen dizesini alır.|  
|[CPictureHolder::GetPictureDispatch](#getpicturedispatch)|Döndürür `CPictureHolder` nesnenin `IDispatch` arabirimi.|  
|[CPictureHolder::GetType](#gettype)|Söyler olup olmadığını `CPictureHolder` nesnesidir bir bit eşlem, meta dosyası ya da bir simge.|  
|[CPictureHolder::Render](#render)|Resmi işler.|  
|[CPictureHolder::SetPictureDispatch](#setpicturedispatch)|Ayarlar `CPictureHolder` nesnenin `IDispatch` arabirimi.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CPictureHolder::m_pPict](#m_ppict)|Resim nesnesi için bir işaretçi.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CPictureHolder` bir taban sınıfı yok.  
  
 Stok resim özelliğiyle Geliştirici bit eşlem, simge veya görüntü için meta dosyası belirtebilirsiniz.  
  
 Özel Resim özellikleri oluşturma hakkında daha fazla bilgi için bkz: [MFC ActiveX denetimleri: ActiveX denetimindeki resimleri kullanarak](../../mfc/mfc-activex-controls-using-pictures-in-an-activex-control.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `CPictureHolder`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxctl.h  
  
##  <a name="cpictureholder"></a>  CPictureHolder::CPictureHolder  
 Oluşturan bir `CPictureHolder` nesnesi.  
  
```  
CPictureHolder();
```  
  
##  <a name="createempty"></a>  CPictureHolder::CreateEmpty  
 Boş bir oluşturur `CPictureHolder` nesne ve ona bağlanan bir `IPicture` arabirimi.  
  
```  
BOOL CreateEmpty();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Nesne başarıyla oluşturulduysa sıfır olmayan; Aksi takdirde 0.  
  
##  <a name="createfrombitmap"></a>  CPictureHolder::CreateFromBitmap  
 Bir bit eşlem resim nesneyi başlatmak için kullandığı bir `CPictureHolder`.  
  
```  
BOOL CreateFromBitmap(
    UINT idResource);

 
BOOL CreateFromBitmap(
    CBitmap* pBitmap,  
    CPalette* pPal = NULL,  
    BOOL bTransferOwnership = TRUE);

 
BOOL CreateFromBitmap(
    HBITMAP hbm,  
    HPALETTE hpal = NULL,  
    BOOL bTransferOwnership = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 `idResource`  
 Bir bit eşlem kaynağının kaynak kimliği.  
  
 `pBitmap`  
 İşaretçi bir [CBitmap](../../mfc/reference/cbitmap-class.md) nesnesi.  
  
 *pPal*  
 İşaretçi bir [CPalette](../../mfc/reference/cpalette-class.md) nesnesi.  
  
 `bTransferOwnership`  
 Resim nesnesi bit eşlem ve palet nesnelerinin sahipliğini alıp almayacağını gösterir.  
  
 `hbm`  
 İşlemek için bit eşlem içinden `CPictureHolder` nesnesi oluşturulur.  
  
 `hpal`  
 Bit eşlem çizmek için kullanılan palet için işleyin.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Nesne başarıyla oluşturulduysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `bTransferOwnership` olan **doğru**, çağıran bit eşlem kullanmamanız gerekir veya bu çağrıyı sonra herhangi bir şekilde palet nesnesini döndürür. Varsa `bTransferOwnership` olan **yanlış**, bit eşlem ve palet nesneleri resim nesnesinin ömrü boyunca geçerli kalmasını sağlamak için çağıran sorumludur.  
  
##  <a name="createfromicon"></a>  CPictureHolder::CreateFromIcon  
 Resim nesneyi başlatmak için bir simge kullanan bir `CPictureHolder`.  
  
```  
BOOL CreateFromIcon(
    UINT idResource);

 
BOOL CreateFromIcon(
    HICON hIcon,  
    BOOL bTransferOwnership = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 `idResource`  
 Bir bit eşlem kaynağının kaynak kimliği.  
  
 `hIcon`  
 İşlemek için simge içinden `CPictureHolder` nesnesi oluşturulur.  
  
 `bTransferOwnership`  
 Resim nesnesi simgesi nesnenin sahipliğini alıp almayacağını gösterir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Nesne başarıyla oluşturulduysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `bTransferOwnership` olan **doğru**, bu çağrıyı döndükten sonra çağıran simgesi nesne herhangi bir şekilde kullanmamanız gerekir. Varsa `bTransferOwnership` olan **yanlış**, çağıran simgesi nesne resim nesnesinin ömrü boyunca geçerli olmasını sağlarken sorumludur.  
  
##  <a name="createfrommetafile"></a>  CPictureHolder::CreateFromMetafile  
 Resim nesneyi başlatmak için bir meta dosyası kullanan bir `CPictureHolder`.  
  
```  
BOOL CreateFromMetafile(
    HMETAFILE hmf,  
    int xExt,  
    int yExt,  
    BOOL bTransferOwnership = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 `hmf`  
 Tanıtıcı oluşturmak için kullanılan meta `CPictureHolder` nesnesi.  
  
 *xExt*  
 Resim kapsamını x.  
  
 *yExt*  
 Resmin Y uzantı.  
  
 `bTransferOwnership`  
 Resim nesnesinin meta dosyası nesnenin sahipliğini alıp almayacağını gösterir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Nesne başarıyla oluşturulduysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `bTransferOwnership` olan **doğru**, bu çağrıyı döndükten sonra çağıran meta dosyası nesne herhangi bir şekilde kullanmamanız gerekir. Varsa `bTransferOwnership` olan **yanlış**, meta dosyası nesne resim nesnesinin ömrü boyunca geçerli olmasını sağlarken çağıran sorumludur.  
  
##  <a name="getdisplaystring"></a>  CPictureHolder::GetDisplayString  
 Bir kapsayıcının özelliği tarayıcıda görüntülenen dizesini alır.  
  
```  
BOOL GetDisplayString(CString& strValue);
```  
  
### <a name="parameters"></a>Parametreler  
 `strValue`  
 Başvuru [CString](../../atl-mfc-shared/reference/cstringt-class.md) diğer bir deyişle görüntü dizesini tutun.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dize başarıyla alınırsa sıfır olmayan; Aksi takdirde 0.  
  
##  <a name="getpicturedispatch"></a>  CPictureHolder::GetPictureDispatch  
 Bu işlev bir işaretçi döndürür `CPictureHolder` nesnenin `IPictureDisp` arabirimi.  
  
```  
LPPICTUREDISP GetPictureDispatch();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi `CPictureHolder` nesnenin `IPictureDisp` arabirimi.  
  
### <a name="remarks"></a>Açıklamalar  
 Arayan çağırmalısınız **sürüm** ile bittiğinde, bu işaretçinin üzerinde.  
  
##  <a name="gettype"></a>  CPictureHolder::GetType  
 Resmi bir bit eşlem, meta dosyası veya simge olup olmadığını gösterir.  
  
```  
short GetType();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Resim türünü belirten bir değer. Olası değerler ve anlamları şu şekildedir:  
  
|Değer|Açıklama|  
|-----------|-------------|  
|**PICTYPE_UNINITIALIZED**|`CPictureHolder` Nesne unititialized.|  
|**PICTYPE_NONE**|`CPictureHolder` Nesne boştur.|  
|**PICTYPE_BITMAP**|Bir bit eşlem resim bulunur.|  
|**PICTYPE_METAFILE**|Resim meta dosyası bulunur.|  
|**PICTYPE_ICON**|Resmi bir simgedir.|  
  
##  <a name="m_ppict"></a>  CPictureHolder::m_pPict  
 Bir işaretçi `CPictureHolder` nesnenin `IPicture` arabirimi.  
  
```  
LPPICTURE m_pPict;  
```  
  
##  <a name="render"></a>  CPictureHolder::Render  
 Tarafından başvurulan dikdörtgen resimde işler `rcRender`.  
  
```  
void Render(
    CDC* pDC,  
    const CRect& rcRender,  
    const CRect& rcWBounds);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDC`  
 Resim işlenmek üzere olduğu görüntüleme bağlamı işaretçi.  
  
 `rcRender`  
 İşlenecek resim olan dikdörtgen.  
  
 *rcWBounds*  
 Resim işleme nesnesinin sınırlayıcı dikdörtgenini temsil eden bir dikdörtgen. Bir denetim için olan bu dikdörtgenin `rcBounds` parametresi için geçersiz kılma geçirilen [COleControl::OnDraw](../../mfc/reference/colecontrol-class.md#ondraw).  
  
##  <a name="setpicturedispatch"></a>  CPictureHolder::SetPictureDispatch  
 Bağlanan `CPictureHolder` nesnesine bir `IPictureDisp` arabirimi.  
  
```  
void SetPictureDispatch(LPPICTUREDISP pDisp);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDisp`  
 İşaretçi yeni `IPictureDisp` arabirimi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CFontHolder Sınıfı](../../mfc/reference/cfontholder-class.md)
