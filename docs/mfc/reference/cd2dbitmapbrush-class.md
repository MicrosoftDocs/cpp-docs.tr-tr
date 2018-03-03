---
title: "CD2DBitmapBrush sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DBitmapBrush
- AFXRENDERTARGET/CD2DBitmapBrush
- AFXRENDERTARGET/CD2DBitmapBrush::CD2DBitmapBrush
- AFXRENDERTARGET/CD2DBitmapBrush::Attach
- AFXRENDERTARGET/CD2DBitmapBrush::Create
- AFXRENDERTARGET/CD2DBitmapBrush::Destroy
- AFXRENDERTARGET/CD2DBitmapBrush::Detach
- AFXRENDERTARGET/CD2DBitmapBrush::Get
- AFXRENDERTARGET/CD2DBitmapBrush::GetBitmap
- AFXRENDERTARGET/CD2DBitmapBrush::GetExtendModeX
- AFXRENDERTARGET/CD2DBitmapBrush::GetExtendModeY
- AFXRENDERTARGET/CD2DBitmapBrush::GetInterpolationMode
- AFXRENDERTARGET/CD2DBitmapBrush::SetBitmap
- AFXRENDERTARGET/CD2DBitmapBrush::SetExtendModeX
- AFXRENDERTARGET/CD2DBitmapBrush::SetExtendModeY
- AFXRENDERTARGET/CD2DBitmapBrush::SetInterpolationMode
- AFXRENDERTARGET/CD2DBitmapBrush::CommonInit
- AFXRENDERTARGET/CD2DBitmapBrush::m_pBitmap
- AFXRENDERTARGET/CD2DBitmapBrush::m_pBitmapBrush
- AFXRENDERTARGET/CD2DBitmapBrush::m_pBitmapBrushProperties
dev_langs:
- C++
helpviewer_keywords:
- CD2DBitmapBrush [MFC], CD2DBitmapBrush
- CD2DBitmapBrush [MFC], Attach
- CD2DBitmapBrush [MFC], Create
- CD2DBitmapBrush [MFC], Destroy
- CD2DBitmapBrush [MFC], Detach
- CD2DBitmapBrush [MFC], Get
- CD2DBitmapBrush [MFC], GetBitmap
- CD2DBitmapBrush [MFC], GetExtendModeX
- CD2DBitmapBrush [MFC], GetExtendModeY
- CD2DBitmapBrush [MFC], GetInterpolationMode
- CD2DBitmapBrush [MFC], SetBitmap
- CD2DBitmapBrush [MFC], SetExtendModeX
- CD2DBitmapBrush [MFC], SetExtendModeY
- CD2DBitmapBrush [MFC], SetInterpolationMode
- CD2DBitmapBrush [MFC], CommonInit
- CD2DBitmapBrush [MFC], m_pBitmap
- CD2DBitmapBrush [MFC], m_pBitmapBrush
- CD2DBitmapBrush [MFC], m_pBitmapBrushProperties
ms.assetid: 46ebbe34-66e0-44c8-af1d-d129e851de5e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3dd588a26b73fb6e5f1b205b20f21aab8272c439
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cd2dbitmapbrush-class"></a>CD2DBitmapBrush sınıfı
ID2D1BitmapBrush için sarmalayıcı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CD2DBitmapBrush : public CD2DBrush;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CD2DBitmapBrush::CD2DBitmapBrush](#cd2dbitmapbrush)|Fazla Yüklendi. Dosyadan CD2DBitmapBrush nesnesi oluşturur.|  
|[CD2DBitmapBrush:: ~ CD2DBitmapBrush](#dtor)|Yok Edicisi. D2D bit eşlem fırça nesnesi yok çağrılır.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CD2DBitmapBrush::Attach](#attach)|Var olan nesne kaynak arabirimine ekler|  
|[CD2DBitmapBrush::Create](#create)|Bir CD2DBitmapBrush oluşturur. (Geçersiz kılmaları [CD2DResource::Create](../../mfc/reference/cd2dresource-class.md#create).)|  
|[CD2DBitmapBrush::Destroy](#destroy)|CD2DBitmapBrush nesnesini yok eder. (Geçersiz kılmaları [CD2DBrush::Destroy](../../mfc/reference/cd2dbrush-class.md#destroy).)|  
|[CD2DBitmapBrush::detach](#detach)|Kaynak arabirimi nesneden çıkarır|  
|[CD2DBitmapBrush::get](#get)|Döndürür ID2D1BitmapBrush arabirimi|  
|[CD2DBitmapBrush::GetBitmap](#getbitmap)|Bu fırça boyamak için kullandığı bit eşlem kaynağını alır|  
|[CD2DBitmapBrush::GetExtendModeX](#getextendmodex)|Tarafından Fırça, bit eşlem genişletmek bu alanları yatay olarak yerleştirir yöntemi alır|  
|[CD2DBitmapBrush::GetExtendModeY](#getextendmodey)|Tarafından Fırça, bit eşlem genişletmek bu alanlara dikey olarak yerleştirir yöntemi alır|  
|[CD2DBitmapBrush::GetInterpolationMode](#getinterpolationmode)|Fırça bit eşlem ölçeklendirilmiş veya Döndürülmüş kullanılan ilişkilendirme yöntemi alır|  
|[CD2DBitmapBrush::SetBitmap](#setbitmap)|Bu fırça boyamak için kullandığı bit eşlem kaynağı belirtir|  
|[CD2DBitmapBrush::SetExtendModeX](#setextendmodex)|Nasıl fırça, bit eşlem genişletmek bu alanları yatay olarak yerleştirir belirtir|  
|[CD2DBitmapBrush::SetExtendModeY](#setextendmodey)|Nasıl fırça, bit eşlem genişletmek bu alanlara dikey olarak yerleştirir belirtir|  
|[CD2DBitmapBrush::SetInterpolationMode](#setinterpolationmode)|Fırça bit eşlem ölçeklendirilmiş veya Döndürülmüş kullanılan ilişkilendirme modunu belirtir.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CD2DBitmapBrush::CommonInit](#commoninit)|Nesneyi başlatır|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CD2DBitmapBrush::operator ID2D1BitmapBrush *](#operator_id2d1bitmapbrush_star)|Döndürür ID2D1BitmapBrush arabirimi|  
  
### <a name="protected-data-members"></a>Korumalı veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CD2DBitmapBrush::m_pBitmap](#m_pbitmap)|CD2DBitmap nesnesine bir işaretçi depolar.|  
|[CD2DBitmapBrush::m_pBitmapBrush](#m_pbitmapbrush)|ID2D1BitmapBrush nesneyi gösteren bir işaretçi depolar.|  
|[CD2DBitmapBrush::m_pBitmapBrushProperties](#m_pbitmapbrushproperties)|Fırça özellikleri bitmap.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DBrush](../../mfc/reference/cd2dbrush-class.md)  
  
 `CD2DBitmapBrush`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxrendertarget.h  
  
##  <a name="dtor"></a>CD2DBitmapBrush:: ~ CD2DBitmapBrush  
 Yok Edicisi. D2D bit eşlem fırça nesnesi yok çağrılır.  
  
```  
virtual ~CD2DBitmapBrush();
```  
  
##  <a name="attach"></a>CD2DBitmapBrush::Attach  
 Var olan nesne kaynak arabirimine ekler  
  
```  
void Attach(ID2D1BitmapBrush* pResource);
```  
  
### <a name="parameters"></a>Parametreler  
 `pResource`  
 Mevcut kaynak arabirimi. NULL olamaz  
  
##  <a name="cd2dbitmapbrush"></a>CD2DBitmapBrush::CD2DBitmapBrush  
 CD2DBitmapBrush nesnesi oluşturur.  
  
```  
CD2DBitmapBrush(
    CRenderTarget* pParentTarget,  
    D2D1_BITMAP_BRUSH_PROPERTIES* pBitmapBrushProperties = NULL,  
    CD2DBrushProperties* pBrushProperties = NULL,  
    BOOL bAutoDestroy = TRUE);

 
CD2DBitmapBrush(
    CRenderTarget* pParentTarget,  
    UINT uiResID,  
    LPCTSTR lpszType = NULL,  
    CD2DSizeU sizeDest = CD2DSizeU(0, 0), 
    D2D1_BITMAP_BRUSH_PROPERTIES* pBitmapBrushProperties = NULL,  
    CD2DBrushProperties* pBrushProperties = NULL,  
    BOOL bAutoDestroy = TRUE);

 
CD2DBitmapBrush(
    CRenderTarget* pParentTarget,  
    LPCTSTR lpszImagePath,  
    CD2DSizeU sizeDest = CD2DSizeU(0, 0), 
    D2D1_BITMAP_BRUSH_PROPERTIES* pBitmapBrushProperties = NULL,  
    CD2DBrushProperties* pBrushProperties = NULL,  
    BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 `pParentTarget`  
 İşleme hedefi için bir işaretçi.  
  
 `pBitmapBrushProperties`  
 Genişletme modları ve bit eşlem fırça ilişkilendirme modu için bir işaretçi.  
  
 `pBrushProperties`  
 Opaklık ve fırça dönüşümü için bir işaretçi.  
  
 `bAutoDestroy`  
 Nesne sahibi (pParentTarget) tarafından yok edilmesi gerektiğini gösterir.  
  
 `uiResID`  
 Kaynak Kimliği kaynak sayısı.  
  
 `lpszType`  
 Kaynak türü içeren null ile sonlandırılmış bir dize işaretçi.  
  
 `sizeDest`  
 Bit eşlem hedef boyutu.  
  
 `lpszImagePath`  
 İşaretçi null ile sonlandırılmış dizeye dosya adını içerir.  
  
##  <a name="commoninit"></a>CD2DBitmapBrush::CommonInit  
 Nesneyi başlatır  
  
```  
void CommonInit(D2D1_BITMAP_BRUSH_PROPERTIES* pBitmapBrushProperties);
```  
  
### <a name="parameters"></a>Parametreler  
 `pBitmapBrushProperties`  
 Bit eşlem Fırça özellikleri için bir işaretçi.  
  
##  <a name="create"></a>CD2DBitmapBrush::Create  
 Bir CD2DBitmapBrush oluşturur.  
  
```  
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```  
  
### <a name="parameters"></a>Parametreler  
 `pRenderTarget`  
 İşleme hedefi için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa, S_OK verir. Aksi takdirde, HRESULT hata kodu döndürür.  
  
##  <a name="destroy"></a>CD2DBitmapBrush::Destroy  
 CD2DBitmapBrush nesnesini yok eder.  
  
```  
virtual void Destroy();
```  
  
##  <a name="detach"></a>CD2DBitmapBrush::detach  
 Kaynak arabirimi nesneden çıkarır  
  
```  
ID2D1BitmapBrush* Detach();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ayrılmış kaynak arabirimi işaretçisi.  
  
##  <a name="get"></a>CD2DBitmapBrush::get  
 Döndürür ID2D1BitmapBrush arabirimi  
  
```  
ID2D1BitmapBrush* Get();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşaretçi bir ID2D1BitmapBrush arabirimi veya nesnesi henüz başlatılmadı yoksa NULL.  
  
##  <a name="getbitmap"></a>CD2DBitmapBrush::GetBitmap  
 Bu fırça boyamak için kullandığı bit eşlem kaynağını alır  
  
```  
CD2DBitmap* GetBitmap();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşaretçi CD2DBitmap nesneye veya nesnesi henüz başlatılmadı yoksa NULL.  
  
##  <a name="getextendmodex"></a>CD2DBitmapBrush::GetExtendModeX  
 Tarafından Fırça, bit eşlem genişletmek bu alanları yatay olarak yerleştirir yöntemi alır  
  
```  
D2D1_EXTEND_MODE GetExtendModeX() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Nasıl fırça, bit eşlem genişletmek bu alanları yatay olarak yerleştirir belirten bir değer  
  
##  <a name="getextendmodey"></a>CD2DBitmapBrush::GetExtendModeY  
 Tarafından Fırça, bit eşlem genişletmek bu alanlara dikey olarak yerleştirir yöntemi alır  
  
```  
D2D1_EXTEND_MODE GetExtendModeY() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Nasıl fırça, bit eşlem genişletmek bu alanlara dikey olarak yerleştirir belirten bir değer  
  
##  <a name="getinterpolationmode"></a>CD2DBitmapBrush::GetInterpolationMode  
 Fırça bit eşlem ölçeklendirilmiş veya Döndürülmüş kullanılan ilişkilendirme yöntemi alır  
  
```  
D2D1_BITMAP_INTERPOLATION_MODE GetInterpolationMode() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Fırça bit eşlem ölçeklendirilmiş veya Döndürülmüş kullanılan ilişkilendirme yöntemi  
  
##  <a name="m_pbitmap"></a>CD2DBitmapBrush::m_pBitmap  
 CD2DBitmap nesnesine bir işaretçi depolar.  
  
```  
CD2DBitmap* m_pBitmap;  
```  
  
##  <a name="m_pbitmapbrush"></a>CD2DBitmapBrush::m_pBitmapBrush  
 ID2D1BitmapBrush nesneyi gösteren bir işaretçi depolar.  
  
```  
ID2D1BitmapBrush* m_pBitmapBrush;  
```  
  
##  <a name="m_pbitmapbrushproperties"></a>CD2DBitmapBrush::m_pBitmapBrushProperties  
 Fırça özellikleri bitmap.  
  
```  
D2D1_BITMAP_BRUSH_PROPERTIES* m_pBitmapBrushProperties;  
```  
  
##  <a name="operator_id2d1bitmapbrush_star"></a>CD2DBitmapBrush::operator ID2D1BitmapBrush *  
 Döndürür ID2D1BitmapBrush arabirimi  
  
```  
operator ID2D1BitmapBrush*();
```   
  
### <a name="return-value"></a>Dönüş Değeri  
 İşaretçi bir ID2D1BitmapBrush arabirimi veya nesnesi henüz başlatılmadı yoksa NULL.  
  
##  <a name="setbitmap"></a>CD2DBitmapBrush::SetBitmap  
 Bu fırça boyamak için kullandığı bit eşlem kaynağı belirtir  
  
```  
void SetBitmap(CD2DBitmap* pBitmap);
```  
  
### <a name="parameters"></a>Parametreler  
 `pBitmap`  
 Fırça tarafından kullanılan bit eşlem kaynağı  
  
##  <a name="setextendmodex"></a>CD2DBitmapBrush::SetExtendModeX  
 Nasıl fırça, bit eşlem genişletmek bu alanları yatay olarak yerleştirir belirtir  
  
```  
void SetExtendModeX(D2D1_EXTEND_MODE extendModeX);
```  
  
### <a name="parameters"></a>Parametreler  
 `extendModeX`  
 Nasıl fırça, bit eşlem genişletmek bu alanları yatay olarak yerleştirir belirten bir değer  
  
##  <a name="setextendmodey"></a>CD2DBitmapBrush::SetExtendModeY  
 Nasıl fırça, bit eşlem genişletmek bu alanlara dikey olarak yerleştirir belirtir  
  
```  
void SetExtendModeY(D2D1_EXTEND_MODE extendModeY);
```  
  
### <a name="parameters"></a>Parametreler  
 `extendModeY`  
 Nasıl fırça, bit eşlem genişletmek bu alanlara dikey olarak yerleştirir belirten bir değer  
  
##  <a name="setinterpolationmode"></a>CD2DBitmapBrush::SetInterpolationMode  
 Fırça bit eşlem ölçeklendirilmiş veya Döndürülmüş kullanılan ilişkilendirme modunu belirtir.  
  
```  
void SetInterpolationMode(D2D1_BITMAP_INTERPOLATION_MODE interpolationMode);
```  
  
### <a name="parameters"></a>Parametreler  
 `interpolationMode`  
 Fırça bit eşlem ölçeklendirilmiş veya Döndürülmüş kullanılan ilişkilendirme modu  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıflar](../../mfc/reference/mfc-classes.md)
