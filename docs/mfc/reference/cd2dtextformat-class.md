---
title: "CD2DTextFormat sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DTextFormat
- AFXRENDERTARGET/CD2DTextFormat
- AFXRENDERTARGET/CD2DTextFormat::CD2DTextFormat
- AFXRENDERTARGET/CD2DTextFormat::Create
- AFXRENDERTARGET/CD2DTextFormat::Destroy
- AFXRENDERTARGET/CD2DTextFormat::Get
- AFXRENDERTARGET/CD2DTextFormat::GetFontFamilyName
- AFXRENDERTARGET/CD2DTextFormat::GetLocaleName
- AFXRENDERTARGET/CD2DTextFormat::IsValid
- AFXRENDERTARGET/CD2DTextFormat::ReCreate
- AFXRENDERTARGET/CD2DTextFormat::m_pTextFormat
dev_langs: C++
helpviewer_keywords:
- CD2DTextFormat [MFC], CD2DTextFormat
- CD2DTextFormat [MFC], Create
- CD2DTextFormat [MFC], Destroy
- CD2DTextFormat [MFC], Get
- CD2DTextFormat [MFC], GetFontFamilyName
- CD2DTextFormat [MFC], GetLocaleName
- CD2DTextFormat [MFC], IsValid
- CD2DTextFormat [MFC], ReCreate
- CD2DTextFormat [MFC], m_pTextFormat
ms.assetid: db194cec-9dae-4644-ab84-7c43b7164117
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1a2c8dbf78fdf7ea8f895b4eb1a4d9a97bbc3ee5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cd2dtextformat-class"></a>CD2DTextFormat sınıfı
IDWriteTextFormat için sarmalayıcı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CD2DTextFormat : public CD2DResource;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CD2DTextFormat::CD2DTextFormat](#cd2dtextformat)|CD2DTextFormat nesnesi oluşturur.|  
|[CD2DTextFormat:: ~ CD2DTextFormat](#cd2dtextformat__~cd2dtextformat)|Yok Edicisi. D2D metin biçimi nesnesi yok çağrılır.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CD2DTextFormat::Create](#create)|Bir CD2DTextFormat oluşturur. (Geçersiz kılmaları [CD2DResource::Create](../../mfc/reference/cd2dresource-class.md#create).)|  
|[CD2DTextFormat::Destroy](#destroy)|CD2DTextFormat nesnesini yok eder. (Geçersiz kılmaları [CD2DResource::Destroy](../../mfc/reference/cd2dresource-class.md#destroy).)|  
|[CD2DTextFormat::get](#get)|Döndürür IDWriteTextFormat arabirimi|  
|[CD2DTextFormat::GetFontFamilyName](#getfontfamilyname)|Yazı tipi ailesinin adı bir kopyasını alır.|  
|[CD2DTextFormat::GetLocaleName](#getlocalename)|Yerel ayar adı bir kopyasını alır.|  
|[CD2DTextFormat::IsValid](#isvalid)|Kaynak geçerlilik denetler (geçersiz kılmaları [CD2DResource::IsValid](../../mfc/reference/cd2dresource-class.md#isvalid).)|  
|[CD2DTextFormat::ReCreate](#recreate)|Bir CD2DTextFormat yeniden oluşturur. (Geçersiz kılmaları [CD2DResource::ReCreate](../../mfc/reference/cd2dresource-class.md#recreate).)|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CD2DTextFormat::operator IDWriteTextFormat *](#operator_idwritetextformat_star)|Döndürür IDWriteTextFormat arabirimi|  
  
### <a name="protected-data-members"></a>Korumalı veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CD2DTextFormat::m_pTextFormat](#m_ptextformat)|Bir IDWriteTextFormat gösteren bir işaretçi.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DTextFormat](../../mfc/reference/cd2dtextformat-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxrendertarget.h  
  
##  <a name="_dtorcd2dtextformat"></a>CD2DTextFormat:: ~ CD2DTextFormat  
 Yok Edicisi. D2D metin biçimi nesnesi yok çağrılır.  
  
```  
virtual ~CD2DTextFormat();
```  
  
##  <a name="cd2dtextformat"></a>CD2DTextFormat::CD2DTextFormat  
 CD2DTextFormat nesnesi oluşturur.  
  
```  
CD2DTextFormat(
    CRenderTarget* pParentTarget,  
    const CString& strFontFamilyName,  
    FLOAT fontSize,  
    DWRITE_FONT_WEIGHT fontWeight = DWRITE_FONT_WEIGHT_NORMAL,  
    DWRITE_FONT_STYLE fontStyle = DWRITE_FONT_STYLE_NORMAL,  
    DWRITE_FONT_STRETCH fontStretch = DWRITE_FONT_STRETCH_NORMAL,  
    const CString& strFontLocale = _T(""),  
    IDWriteFontCollection* pFontCollection = NULL,  
    BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 `pParentTarget`  
 İşleme hedefi için bir işaretçi.  
  
 `strFontFamilyName`  
 Yazı tipi ailesinin adını içeren bir CString nesnesi.  
  
 `fontSize`  
 Yazı tipi DIP ("aygıttan bağımsız piksel") birimlerindeki mantıksal boyutu. Bir DIPequals 1/96 inç.  
  
 `fontWeight`  
 Metin nesnesi için yazı tipi ağırlığı belirten bir değer.  
  
 `fontStyle`  
 Metin nesnesi için yazı tipi stilini gösteren bir değer.  
  
 `fontStretch`  
 Metin nesnesi için yazı tipi esnetme belirten bir değer.  
  
 `strFontLocale`  
 Yerel ayar adı içeren bir CString nesnesi.  
  
 `pFontCollection`  
 Yazı tipi koleksiyon nesnesi için bir işaretçi. Bu NULL olduğunda, sistem yazı tipi koleksiyonu gösterir.  
  
 `bAutoDestroy`  
 Nesne sahibi (pParentTarget) tarafından yok edilmesi gerektiğini gösterir.  
  
##  <a name="create"></a>CD2DTextFormat::Create  
 Bir CD2DTextFormat oluşturur.  
  
```  
virtual HRESULT Create(CRenderTarget* */);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa, S_OK verir. Aksi takdirde, HRESULT hata kodu döndürür.  
  
##  <a name="destroy"></a>CD2DTextFormat::Destroy  
 CD2DTextFormat nesnesini yok eder.  
  
```  
virtual void Destroy();
```  
  
##  <a name="get"></a>CD2DTextFormat::get  
 Döndürür IDWriteTextFormat arabirimi  
  
```  
IDWriteTextFormat* Get();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşaretçi bir IDWriteTextFormat arabirimi veya nesnesi henüz başlatılmadı yoksa NULL.  
  
##  <a name="getfontfamilyname"></a>CD2DTextFormat::GetFontFamilyName  
 Yazı tipi ailesinin adı bir kopyasını alır.  
  
```  
CString GetFontFamilyName() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli yazı tipi ailesinin adı içeren CString nesne.  
  
##  <a name="getlocalename"></a>CD2DTextFormat::GetLocaleName  
 Yerel ayar adı bir kopyasını alır.  
  
```  
CString GetLocaleName() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli yerel ayar adını içeren CString nesne.  
  
##  <a name="isvalid"></a>CD2DTextFormat::IsValid  
 Denetimleri kaynak geçerlilik  
  
```  
virtual BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kaynağın geçerli ise TRUE; Aksi takdirde FALSE.  
  
##  <a name="m_ptextformat"></a>CD2DTextFormat::m_pTextFormat  
 Bir IDWriteTextFormat gösteren bir işaretçi.  
  
```  
IDWriteTextFormat* m_pTextFormat;  
```  
  
##  <a name="operator_idwritetextformat_star"></a>CD2DTextFormat::operator IDWriteTextFormat *  
 Döndürür IDWriteTextFormat arabirimi  
  
```  
operator IDWriteTextFormat*();
```   
  
### <a name="return-value"></a>Dönüş Değeri  
 İşaretçi bir IDWriteTextFormat arabirimi veya nesnesi henüz başlatılmadı yoksa NULL.  
  
##  <a name="recreate"></a>CD2DTextFormat::ReCreate  
 Bir CD2DTextFormat yeniden oluşturur.  
  
```  
virtual HRESULT ReCreate(CRenderTarget* */);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa, S_OK verir. Aksi takdirde, HRESULT hata kodu döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfları](../../mfc/reference/mfc-classes.md)
