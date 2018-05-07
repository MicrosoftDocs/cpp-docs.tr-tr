---
title: CD2DBitmap sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CD2DBitmap
- AFXRENDERTARGET/CD2DBitmap
- AFXRENDERTARGET/CD2DBitmap::CD2DBitmap
- AFXRENDERTARGET/CD2DBitmap::Attach
- AFXRENDERTARGET/CD2DBitmap::CopyFromBitmap
- AFXRENDERTARGET/CD2DBitmap::CopyFromMemory
- AFXRENDERTARGET/CD2DBitmap::CopyFromRenderTarget
- AFXRENDERTARGET/CD2DBitmap::Create
- AFXRENDERTARGET/CD2DBitmap::Destroy
- AFXRENDERTARGET/CD2DBitmap::Detach
- AFXRENDERTARGET/CD2DBitmap::Get
- AFXRENDERTARGET/CD2DBitmap::GetDPI
- AFXRENDERTARGET/CD2DBitmap::GetPixelFormat
- AFXRENDERTARGET/CD2DBitmap::GetPixelSize
- AFXRENDERTARGET/CD2DBitmap::GetSize
- AFXRENDERTARGET/CD2DBitmap::IsValid
- AFXRENDERTARGET/CD2DBitmap::CommonInit
- AFXRENDERTARGET/CD2DBitmap::m_bAutoDestroyHBMP
- AFXRENDERTARGET/CD2DBitmap::m_hBmpSrc
- AFXRENDERTARGET/CD2DBitmap::m_lpszType
- AFXRENDERTARGET/CD2DBitmap::m_pBitmap
- AFXRENDERTARGET/CD2DBitmap::m_sizeDest
- AFXRENDERTARGET/CD2DBitmap::m_strPath
- AFXRENDERTARGET/CD2DBitmap::m_uiResID
dev_langs:
- C++
helpviewer_keywords:
- CD2DBitmap [MFC], CD2DBitmap
- CD2DBitmap [MFC], CD2DBitmap
- CD2DBitmap [MFC], Attach
- CD2DBitmap [MFC], CopyFromBitmap
- CD2DBitmap [MFC], CopyFromMemory
- CD2DBitmap [MFC], CopyFromRenderTarget
- CD2DBitmap [MFC], Create
- CD2DBitmap [MFC], Destroy
- CD2DBitmap [MFC], Detach
- CD2DBitmap [MFC], Get
- CD2DBitmap [MFC], GetDPI
- CD2DBitmap [MFC], GetPixelFormat
- CD2DBitmap [MFC], GetPixelSize
- CD2DBitmap [MFC], GetSize
- CD2DBitmap [MFC], IsValid
- CD2DBitmap [MFC], CommonInit
- CD2DBitmap [MFC], m_bAutoDestroyHBMP
- CD2DBitmap [MFC], m_hBmpSrc
- CD2DBitmap [MFC], m_lpszType
- CD2DBitmap [MFC], m_pBitmap
- CD2DBitmap [MFC], m_sizeDest
- CD2DBitmap [MFC], m_strPath
- CD2DBitmap [MFC], m_uiResID
ms.assetid: 2b3686f1-812c-462b-b449-9f0cb6949bf6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b92587d6cad3004c87ee6aee4716888d09c1270a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="cd2dbitmap-class"></a>CD2DBitmap sınıfı
ID2D1Bitmap için sarmalayıcı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CD2DBitmap : public CD2DResource;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CD2DBitmap::CD2DBitmap](#cd2dbitmap)|Fazla Yüklendi. HBITMAP CD2DBitmap nesnesinden oluşturur.|  
|[CD2DBitmap:: ~ CD2DBitmap](#_dtorcd2dbitmap)|Yok Edicisi. D2D bit eşlem nesnesi yok çağrılır.|  
  
### <a name="protected-constructors"></a>Korumalı Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CD2DBitmap::CD2DBitmap](#cd2dbitmap)|Fazla Yüklendi. CD2DBitmap nesnesi oluşturur.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CD2DBitmap::Attach](#attach)|Var olan nesne kaynak arabirimine ekler|  
|[CD2DBitmap::CopyFromBitmap](#copyfrombitmap)|Belirtilen bölge belirtilen bit eşlem geçerli bitmap içine kopyalar.|  
|[CD2DBitmap::CopyFromMemory](#copyfrommemory)|Belirtilen bölge bellekten geçerli bitmap içine kopyalar.|  
|[CD2DBitmap::CopyFromRenderTarget](#copyfromrendertarget)|Kopya belirtilen belirtilen bölgesinden işlemek hedef geçerli bit eşlem|  
|[CD2DBitmap::Create](#create)|Bir CD2DBitmap oluşturur. (Geçersiz kılmaları [CD2DResource::Create](../../mfc/reference/cd2dresource-class.md#create).)|  
|[CD2DBitmap::Destroy](#destroy)|CD2DBitmap nesnesini yok eder. (Geçersiz kılmaları [CD2DResource::Destroy](../../mfc/reference/cd2dresource-class.md#destroy).)|  
|[CD2DBitmap::detach](#detach)|Kaynak arabirimi nesneden çıkarır|  
|[CD2DBitmap::get](#get)|Döndürür ID2D1Bitmap arabirimi|  
|[CD2DBitmap::GetDPI](#getdpi)|Nokta / inç (DPI) bit eşlem Döndür|  
|[CD2DBitmap::GetPixelFormat](#getpixelformat)|Bit eşlem piksel biçimi ve alfa modunu alır.|  
|[CD2DBitmap::GetPixelSize](#getpixelsize)|Aygıta bağımlı birimler (piksel) boyutu, bit eşlem döndürür|  
|[CD2DBitmap::GetSize](#getsize)|Bit eşlem (Dıps) aygıttan bağımsız piksel cinsinden boyutu döndürür|  
|[CD2DBitmap::IsValid](#isvalid)|Kaynak geçerlilik denetler (geçersiz kılmaları [CD2DResource::IsValid](../../mfc/reference/cd2dresource-class.md#isvalid).)|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CD2DBitmap::CommonInit](#commoninit)|Nesneyi başlatır|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CD2DBitmap::operator ID2D1Bitmap *](#operator_id2d1bitmap_star)|Döndürür ID2D1Bitmap arabirimi|  
  
### <a name="protected-data-members"></a>Korumalı veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CD2DBitmap::m_bAutoDestroyHBMP](#m_bautodestroyhbmp)|M_hBmpSrc yok edilmesi TRUE; Aksi takdirde FALSE.|  
|[CD2DBitmap::m_hBmpSrc](#m_hbmpsrc)|Kaynak eşlem tanıtıcısı.|  
|[CD2DBitmap::m_lpszType](#m_lpsztype)|Kaynak türü.|  
|[CD2DBitmap::m_pBitmap](#m_pbitmap)|ID2D1Bitmap nesneyi gösteren bir işaretçi depolar.|  
|[CD2DBitmap::m_sizeDest](#m_sizedest)|Hedef boyutu bitmap.|  
|[CD2DBitmap::m_strPath](#m_strpath)|Botmap dosya yolu.|  
|[CD2DBitmap::m_uiResID](#m_uiresid)|Bit eşlem kaynak kimliği|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 `CD2DBitmap`
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxrendertarget.h  
  
##  <a name="_dtorcd2dbitmap"></a>  CD2DBitmap:: ~ CD2DBitmap  
 Yok Edicisi. D2D bit eşlem nesnesi yok çağrılır.  
  
```  
virtual ~CD2DBitmap();
```  
  
##  <a name="attach"></a>  CD2DBitmap::Attach  
 Var olan nesne kaynak arabirimine ekler  
  
```  
void Attach(ID2D1Bitmap* pResource);
```  
  
### <a name="parameters"></a>Parametreler  
 `pResource`  
 Mevcut kaynak arabirimi. NULL olamaz  
  
##  <a name="cd2dbitmap"></a>  CD2DBitmap::CD2DBitmap  
 Kaynak CD2DBitmap nesnesinden oluşturur.  
  
```  
CD2DBitmap(
    CRenderTarget* pParentTarget,  
    UINT uiResID,  
    LPCTSTR lpszType = NULL,  
    CD2DSizeU sizeDest = CD2DSizeU(0, 0), 
    BOOL bAutoDestroy = TRUE);

 
CD2DBitmap(
    CRenderTarget* pParentTarget,  
    LPCTSTR lpszPath,  
    CD2DSizeU sizeDest = CD2DSizeU(0, 0), 
    BOOL bAutoDestroy = TRUE);

 
CD2DBitmap(
    CRenderTarget* pParentTarget,  
    HBITMAP hbmpSrc,  
    CD2DSizeU sizeDest = CD2DSizeU(0, 0), 
    BOOL bAutoDestroy = TRUE);

 
CD2DBitmap(
    CRenderTarget* pParentTarget,  
    BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 `pParentTarget`  
 İşleme hedefi için bir işaretçi.  
  
 `uiResID`  
 Kaynak Kimliği kaynak sayısı.  
  
 `lpszType`  
 Kaynak türü içeren null ile sonlandırılmış bir dize işaretçi.  
  
 `sizeDest`  
 Bit eşlem hedef boyutu.  
  
 `bAutoDestroy`  
 Nesne sahibi (pParentTarget) tarafından yok edilmesi gerektiğini gösterir.  
  
 `lpszPath`  
 İşaretçi null ile sonlandırılmış dizeye dosya adını içerir.  
  
 `hbmpSrc`  
 Bit eşlem için işler.  
  
##  <a name="commoninit"></a>  CD2DBitmap::CommonInit  
 Nesneyi başlatır  
  
```  
void CommonInit();
```  
  
##  <a name="copyfrombitmap"></a>  CD2DBitmap::CopyFromBitmap  
 Belirtilen bölge belirtilen bit eşlem geçerli bitmap içine kopyalar.  
  
```  
HRESULT CopyFromBitmap(
    const CD2DBitmap* pBitmap,  
    const CD2DPointU* destPoint = NULL,  
    const CD2DRectU* srcRect = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `pBitmap`  
 Kopyalanacak bit eşlem  
  
 `destPoint`  
 Geçerli bit eşlem için bölge srcRect tarafından belirtilen alan sol üst köşesindeki kopyalanır.  
  
 `srcRect`  
 Bit eşlem kopyalamak için alanı  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa, S_OK verir. Aksi takdirde, HRESULT hata kodu döndürür.  
  
##  <a name="copyfrommemory"></a>  CD2DBitmap::CopyFromMemory  
 Belirtilen bölge bellekten geçerli bitmap içine kopyalar.  
  
```  
HRESULT CopyFromMemory(
    const void* srcData,  
    UINT32 pitch,  
    const CD2DRectU* destRect = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `srcData`  
 Kopyalanacak veriler  
  
 `pitch`  
 STRIDE veya srcData içinde depolanan kaynak bit eşlem aralık. STRIDE tarama satırı (piksel cinsinden bellek bir satır) bayt sayısıdır. STRIDE aşağıdaki formülünden hesaplanan değer: piksel genişlik * piksel + bellek doldurma başına bayt sayısı  
  
 `destRect`  
 Geçerli bit eşlem için bölge srcRect tarafından belirtilen alan sol üst köşesindeki kopyalanır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa, S_OK verir. Aksi takdirde, HRESULT hata kodu döndürür.  
  
##  <a name="copyfromrendertarget"></a>  CD2DBitmap::CopyFromRenderTarget  
 Kopya belirtilen belirtilen bölgesinden işlemek hedef geçerli bit eşlem  
  
```  
HRESULT CopyFromRenderTarget(
    const CRenderTarget* pRenderTarget,  
    const CD2DPointU* destPoint = NULL,  
    const CD2DRectU* srcRect = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `pRenderTarget`  
 Kopyalamak için bölgesi içeren işleme hedefi  
  
 `destPoint`  
 Geçerli bit eşlem için bölge srcRect tarafından belirtilen alan sol üst köşesindeki kopyalanır.  
  
 `srcRect`  
 Kopyalamak için işlem hedefi alanı  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa, S_OK verir. Aksi takdirde, HRESULT hata kodu döndürür.  
  
##  <a name="create"></a>  CD2DBitmap::Create  
 Bir CD2DBitmap oluşturur.  
  
```  
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```  
  
### <a name="parameters"></a>Parametreler  
 `pRenderTarget`  
 İşleme hedefi için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa, S_OK verir. Aksi takdirde, HRESULT hata kodu döndürür.  
  
##  <a name="destroy"></a>  CD2DBitmap::Destroy  
 CD2DBitmap nesnesini yok eder.  
  
```  
virtual void Destroy();
```  
  
##  <a name="detach"></a>  CD2DBitmap::detach  
 Kaynak arabirimi nesneden çıkarır  
  
```  
ID2D1Bitmap* Detach();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ayrılmış kaynak arabirimi işaretçisi.  
  
##  <a name="get"></a>  CD2DBitmap::get  
 Döndürür ID2D1Bitmap arabirimi  
  
```  
ID2D1Bitmap* Get();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşaretçi bir ID2D1Bitmap arabirimi veya nesnesi henüz başlatılmadı yoksa NULL.  
  
##  <a name="getdpi"></a>  CD2DBitmap::GetDPI  
 Nokta / inç (DPI) bit eşlem Döndür  
  
```  
CD2DSizeF GetDPI() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bit eşlem yatay ve dikey DPI.  
  
##  <a name="getpixelformat"></a>  CD2DBitmap::GetPixelFormat  
 Bit eşlem piksel biçimi ve alfa modunu alır.  
  
```  
D2D1_PIXEL_FORMAT GetPixelFormat() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bit eşlem piksel biçimi ve alfa modu.  
  
##  <a name="getpixelsize"></a>  CD2DBitmap::GetPixelSize  
 Aygıta bağımlı birimler (piksel) boyutu, bit eşlem döndürür  
  
```  
CD2DSizeU GetPixelSize() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Piksel cinsinden bit eşlem boyutu...  
  
##  <a name="getsize"></a>  CD2DBitmap::GetSize  
 Bit eşlem (Dıps) aygıttan bağımsız piksel cinsinden boyutu döndürür  
  
```  
CD2DSizeF GetSize() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bit eşlem Dıps boyutu.  
  
##  <a name="isvalid"></a>  CD2DBitmap::IsValid  
 Denetimleri kaynak geçerlilik  
  
```  
virtual BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kaynağın geçerli ise TRUE; Aksi takdirde FALSE.  
  
##  <a name="m_bautodestroyhbmp"></a>  CD2DBitmap::m_bAutoDestroyHBMP  
 M_hBmpSrc yok edilmesi TRUE; Aksi takdirde FALSE.  
  
```  
BOOL m_bAutoDestroyHBMP;  
```  
  
##  <a name="m_hbmpsrc"></a>  CD2DBitmap::m_hBmpSrc  
 Kaynak eşlem tanıtıcısı.  
  
```  
HBITMAP m_hBmpSrc;  
```  
  
##  <a name="m_lpsztype"></a>  CD2DBitmap::m_lpszType  
 Kaynak türü.  
  
```  
LPCTSTR m_lpszType;  
```  
  
##  <a name="m_pbitmap"></a>  CD2DBitmap::m_pBitmap  
 ID2D1Bitmap nesneyi gösteren bir işaretçi depolar.  
  
```  
ID2D1Bitmap* m_pBitmap;  
```  
  
##  <a name="m_sizedest"></a>  CD2DBitmap::m_sizeDest  
 Hedef boyutu bitmap.  
  
```  
CD2DSizeU m_sizeDest;  
```  
  
##  <a name="m_strpath"></a>  CD2DBitmap::m_strPath  
 Botmap dosya yolu.  
  
```  
CString m_strPath;  
```  
  
##  <a name="m_uiresid"></a>  CD2DBitmap::m_uiResID  
 Bit eşlem kaynak kimliği  
  
```  
UINT m_uiResID;  
```  
  
##  <a name="operator_id2d1bitmap_star"></a>  CD2DBitmap::operator ID2D1Bitmap *  
 Döndürür ID2D1Bitmap arabirimi  
  
```  
operator ID2D1Bitmap*();
```   
  
### <a name="return-value"></a>Dönüş Değeri  
 İşaretçi bir ID2D1Bitmap arabirimi veya nesnesi henüz başlatılmadı yoksa NULL.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıflar](../../mfc/reference/mfc-classes.md)
