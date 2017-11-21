---
title: "CD2DTextLayout sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DTextLayout
- AFXRENDERTARGET/CD2DTextLayout
- AFXRENDERTARGET/CD2DTextLayout::CD2DTextLayout
- AFXRENDERTARGET/CD2DTextLayout::Create
- AFXRENDERTARGET/CD2DTextLayout::Destroy
- AFXRENDERTARGET/CD2DTextLayout::Get
- AFXRENDERTARGET/CD2DTextLayout::GetFontFamilyName
- AFXRENDERTARGET/CD2DTextLayout::GetLocaleName
- AFXRENDERTARGET/CD2DTextLayout::IsValid
- AFXRENDERTARGET/CD2DTextLayout::ReCreate
- AFXRENDERTARGET/CD2DTextLayout::SetFontFamilyName
- AFXRENDERTARGET/CD2DTextLayout::SetLocaleName
- AFXRENDERTARGET/CD2DTextLayout::m_pTextLayout
dev_langs: C++
helpviewer_keywords:
- CD2DTextLayout [MFC], CD2DTextLayout
- CD2DTextLayout [MFC], Create
- CD2DTextLayout [MFC], Destroy
- CD2DTextLayout [MFC], Get
- CD2DTextLayout [MFC], GetFontFamilyName
- CD2DTextLayout [MFC], GetLocaleName
- CD2DTextLayout [MFC], IsValid
- CD2DTextLayout [MFC], ReCreate
- CD2DTextLayout [MFC], SetFontFamilyName
- CD2DTextLayout [MFC], SetLocaleName
- CD2DTextLayout [MFC], m_pTextLayout
ms.assetid: 724bd13c-f2ef-4e55-a775-8cb04b7b7908
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: bf5a4b554f3ee06c9f7aab60fe615ef9be0e544a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cd2dtextlayout-class"></a>CD2DTextLayout sınıfı
IDWriteTextLayout için sarmalayıcı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CD2DTextLayout : public CD2DResource;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CD2DTextLayout::CD2DTextLayout](#cd2dtextlayout)|CD2DTextLayout nesnesi oluşturur.|  
|[CD2DTextLayout:: ~ CD2DTextLayout](#cd2dtextlayout__~cd2dtextlayout)|Yok Edicisi. D2D metin düzeni nesnesi yok çağrılır.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CD2DTextLayout::Create](#create)|Bir CD2DTextLayout oluşturur. (Geçersiz kılmaları [CD2DResource::Create](../../mfc/reference/cd2dresource-class.md#create).)|  
|[CD2DTextLayout::Destroy](#destroy)|CD2DTextLayout nesnesini yok eder. (Geçersiz kılmaları [CD2DResource::Destroy](../../mfc/reference/cd2dresource-class.md#destroy).)|  
|[CD2DTextLayout::get](#get)|Döndürür IDWriteTextLayout arabirimi|  
|[CD2DTextLayout::GetFontFamilyName](#getfontfamilyname)|Belirli bir konumda metin yazı tipi ailesinin adı kopyalar.|  
|[CD2DTextLayout::GetLocaleName](#getlocalename)|Belirtilen konumda metin yerel ayar adını alır.|  
|[CD2DTextLayout::IsValid](#isvalid)|Kaynak geçerlilik denetler (geçersiz kılmaları [CD2DResource::IsValid](../../mfc/reference/cd2dresource-class.md#isvalid).)|  
|[CD2DTextLayout::ReCreate](#recreate)|Bir CD2DTextLayout yeniden oluşturur. (Geçersiz kılmaları [CD2DResource::ReCreate](../../mfc/reference/cd2dresource-class.md#recreate).)|  
|[CD2DTextLayout::SetFontFamilyName](#setfontfamilyname)|Kümeleri null ile sonlandırılmış yazı tipi ailesinin adı belirtilen metin aralığı içinde metin|  
|[CD2DTextLayout::SetLocaleName](#setlocalename)|Belirtilen metin aralığı içinde metni için yerel ad ayarlar|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CD2DTextLayout::operator IDWriteTextLayout *](#operator_idwritetextlayout_star)|Döndürür IDWriteTextLayout arabirimi|  
  
### <a name="protected-data-members"></a>Korumalı veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CD2DTextLayout::m_pTextLayout](#m_ptextlayout)|Bir IDWriteTextLayout gösteren bir işaretçi.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DTextLayout](../../mfc/reference/cd2dtextlayout-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxrendertarget.h  
  
##  <a name="_dtorcd2dtextlayout"></a>CD2DTextLayout:: ~ CD2DTextLayout  
 Yok Edicisi. D2D metin düzeni nesnesi yok çağrılır.  
  
```  
virtual ~CD2DTextLayout();
```  
  
##  <a name="cd2dtextlayout"></a>CD2DTextLayout::CD2DTextLayout  
 CD2DTextLayout nesnesi oluşturur.  
  
```  
CD2DTextLayout(
    CRenderTarget* pParentTarget,  
    const CString& strText,  
    CD2DTextFormat& textFormat,  
    const CD2DSizeF& sizeMax,  
    BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 `pParentTarget`  
 İşleme hedefi için bir işaretçi.  
  
 `strText`  
 Yeni bir CD2DTextLayout nesne oluşturmak için dizesi içeren bir CString nesnesi.  
  
 `textFormat`  
 Dizeye uygulanacak biçimini içeren bir CString nesnesi.  
  
 `sizeMax`  
 Düzen kutusunun boyutu.  
  
 `bAutoDestroy`  
 Nesne sahibi (pParentTarget) tarafından yok edilmesi gerektiğini gösterir.  
  
##  <a name="create"></a>CD2DTextLayout::Create  
 Bir CD2DTextLayout oluşturur.  
  
```  
virtual HRESULT Create(CRenderTarget* */);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa, S_OK verir. Aksi takdirde, HRESULT hata kodu döndürür.  
  
##  <a name="destroy"></a>CD2DTextLayout::Destroy  
 CD2DTextLayout nesnesini yok eder.  
  
```  
virtual void Destroy();
```  
  
##  <a name="get"></a>CD2DTextLayout::get  
 Döndürür IDWriteTextLayout arabirimi  
  
```  
IDWriteTextLayout* Get();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşaretçi bir IDWriteTextLayout arabirimi veya nesnesi henüz başlatılmadı yoksa NULL.  
  
##  <a name="getfontfamilyname"></a>CD2DTextLayout::GetFontFamilyName  
 Belirli bir konumda metin yazı tipi ailesinin adı kopyalar.  
  
```  
CString GetFontFamilyName(
    UINT32 currentPosition,  
    DWRITE_TEXT_RANGE* textRange = NULL) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `currentPosition`  
 İncelemek için metin konumu.  
  
 `textRange`  
 CurrentPosition tarafından belirtilen konumdaki metin olarak aynı olan metin aralığını biçimlendirme. Bu konumu belirtildi, ancak bunlarla sınırlı olmamak yazı tipi ailesinin adı dahil olmak üzere tam biçimlendirmeleri Çalıştır olduğu anlamına gelir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli yazı tipi ailesinin adı içeren CString nesne.  
  
##  <a name="getlocalename"></a>CD2DTextLayout::GetLocaleName  
 Belirtilen konumda metin yerel ayar adını alır.  
  
```  
CString GetLocaleName(
    UINT32 currentPosition,  
    DWRITE_TEXT_RANGE* textRange = NULL) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `currentPosition`  
 İncelenecek metin konumu.  
  
 `textRange`  
 CurrentPosition tarafından belirtilen konumdaki metin olarak aynı olan metin aralığını biçimlendirme. Bu konumu belirtildi, ancak bunlarla sınırlı olmamak yerel ayar adı dahil olmak üzere tam biçimlendirmeleri Çalıştır olduğu anlamına gelir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli yerel ayar adını içeren CString nesne.  
  
##  <a name="isvalid"></a>CD2DTextLayout::IsValid  
 Denetimleri kaynak geçerlilik  
  
```  
virtual BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kaynağın geçerli ise TRUE; Aksi takdirde FALSE.  
  
##  <a name="m_ptextlayout"></a>CD2DTextLayout::m_pTextLayout  
 Bir IDWriteTextLayout gösteren bir işaretçi.  
  
```  
IDWriteTextLayout* m_pTextLayout;  
```  
  
##  <a name="operator_idwritetextlayout_star"></a>CD2DTextLayout::operator IDWriteTextLayout *  
 Döndürür IDWriteTextLayout arabirimi  
  
```  
operator IDWriteTextLayout*();
```   
  
### <a name="return-value"></a>Dönüş Değeri  
 İşaretçi bir IDWriteTextLayout arabirimi veya nesnesi henüz başlatılmadı yoksa NULL.  
  
##  <a name="recreate"></a>CD2DTextLayout::ReCreate  
 Bir CD2DTextLayout yeniden oluşturur.  
  
```  
virtual HRESULT ReCreate(CRenderTarget* */);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa, S_OK verir. Aksi takdirde, HRESULT hata kodu döndürür.  
  
##  <a name="setfontfamilyname"></a>CD2DTextLayout::SetFontFamilyName  
 Kümeleri null ile sonlandırılmış yazı tipi ailesinin adı belirtilen metin aralığı içinde metin  
  
```  
BOOL SetFontFamilyName(
    LPCWSTR pwzFontFamilyName,  
    DWRITE_TEXT_RANGE textRange);
```  
  
### <a name="parameters"></a>Parametreler  
 `pwzFontFamilyName`  
 Tüm metin dizesini textRange tarafından belirtilen aralıkta uygulandığı yazı tipi ailesinin adı  
  
 `textRange`  
 Bu değişiklik uygulandığı metin aralığı  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa TRUE değerini döndürür. Aksi takdirde FALSE değerini döndürür  
  
##  <a name="setlocalename"></a>CD2DTextLayout::SetLocaleName  
 Belirtilen metin aralığı içinde metni için yerel ad ayarlar  
  
```  
BOOL SetLocaleName(
    LPCWSTR pwzLocaleName,  
    DWRITE_TEXT_RANGE textRange);
```  
  
### <a name="parameters"></a>Parametreler  
 `pwzLocaleName`  
 Sonlandırılmış yerel ad dizesi  
  
 `textRange`  
 Bu değişiklik uygulandığı metin aralığı  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa TRUE değerini döndürür. Aksi takdirde FALSE değerini döndürür  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfları](../../mfc/reference/mfc-classes.md)
