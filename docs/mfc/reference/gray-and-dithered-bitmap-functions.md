---
title: Gri ve Titremeli bit eşlem işlevleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- AFXWIN/AfxDrawGrayBitmap
- AFXWIN/AfxGetGrayBitmap
- AFXWIN/AfxDrawDitheredBitmap
- AFXWIN/AfxGetDitheredBitmap
dev_langs:
- C++
helpviewer_keywords:
- gray and dithered bitmap functions [MFC]
ms.assetid: cb139a77-b85e-4504-9d93-24156ad77a41
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: de887cdbe80642925bc935eb48726a59850f6f96
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33375180"
---
# <a name="gray-and-dithered-bitmap-functions"></a>Gri ve Titremeli Bit Eşlem İşlevleri
**Gri bit eşlem işlevleri**  
  
 MFC bir bit eşlem devre dışı bırakılmış bir denetimin görünümünü vermiş için iki işlev sağlar.  
  
 ![Gri ve özgün simgesi sürümlerinin karşılaştırması](../../mfc/reference/media/vcgraybitmap.gif "vcgraybitmap")  
  
|||  
|-|-|  
|[AfxDrawGrayBitmap](#afxdrawgraybitmap)|Bir bit eşlem gri sürümü çizer.|  
|[AfxGetGrayBitmap](#afxgetgraybitmap)|Bir bit eşlem gri sürümünü kopyalar.|  
  
 **Titremeli bit eşlem işlevleri**  
  
 MFC bit eşlem ait arka plan Titremeli deseni ile değiştirme için iki işlevleri de sağlar.  
  
 ![Titremeli ve özgün simgesi sürümlerinin karşılaştırması](../../mfc/reference/media/vcditheredbitmap.gif "vcditheredbitmap")  
  
|||  
|-|-|  
|[AfxDrawDitheredBitmap](#afxdrawditheredbitmap)|Titremeli arka plana sahip bir bit eşlem çizer.|  
|[AfxGetDitheredBitmap](#afxgetditheredbitmap)|Titremeli arka plana sahip bir bit eşlem kopyalar.|  
  
##  <a name="afxdrawgraybitmap"></a>  AfxDrawGrayBitmap  
 Bir bit eşlem gri sürümü çizer.  
  
```   
void AFXAPI AfxDrawGrayBitmap(
    CDC* pDC,  
    int x,  
    int y,  
    const CBitmap& rSrc,  
    COLORREF crBackground); 
```  
  
### <a name="parameters"></a>Parametreler  
 `pDC`  
 Hedef DC noktalarına.  
  
 *x*  
 Hedef x koordinatı.  
  
 *Y*  
 Hedef y koordinatı.  
  
 `rSrc`  
 Kaynak bitmap.  
  
 `crBackground`  
 Yeni arka plan rengi (COLOR_MENU gibi genellikle gri).  
  
### <a name="remarks"></a>Açıklamalar  
 İle çizilmiş bir bit eşlem `AfxDrawGrayBitmap` devre dışı bırakılmış bir denetimin görünümünü sahip olur.  
  
 ![Gri ve özgün simgesi sürümlerinin karşılaştırması](../../mfc/reference/media/vcgraybitmap.gif "vcgraybitmap")  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#191](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_1.cpp)]  

### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwin.h  

##  <a name="afxgetgraybitmap"></a>  AfxGetGrayBitmap  
 Bir bit eşlem gri sürümünü kopyalar.  
  
```   
void AFXAPI AfxGetGrayBitmap(
    const CBitmap& rSrc,  
    CBitmap* pDest,  
    COLORREF crBackground); 
```  
  
### <a name="parameters"></a>Parametreler  
 `rSrc`  
 Kaynak bitmap.  
  
 `pDest`  
 Hedef bitmap.  
  
 `crBackground`  
 Yeni arka plan rengi (COLOR_MENU gibi genellikle gri).  
  
### <a name="remarks"></a>Açıklamalar  
 İle bir bit eşlem `AfxGetGrayBitmap` devre dışı bırakılmış bir denetimin görünümünü sahip olur.  
  
 ![Gri ve özgün simgesi sürümlerinin karşılaştırması](../../mfc/reference/media/vcgraybitmap.gif "vcgraybitmap")  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#193](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_2.cpp)]  

### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwin.h  
  
##  <a name="afxdrawditheredbitmap"></a>  AfxDrawDitheredBitmap  
 Arka plan Titremeli (denetleyicisi) deseni ile değiştirme bir bit eşlem çizer.  
  
```   
void AFXAPI AfxDrawDitheredBitmap(
    CDC* pDC,  
    int x,  
    int y,  
    const CBitmap& rSrc,  
    COLORREF cr1  ,  
    COLORREF cr2); 
```  
  
### <a name="parameters"></a>Parametreler  
 `pDC`  
 Hedef DC noktalarına.  
  
 *x*  
 Hedef x koordinatı.  
  
 *Y*  
 Hedef y koordinatı.  
  
 `rSrc`  
 Kaynak bitmap.  
  
 `cr1`  
 Genellikle iki taklit renkleri birini beyaz.  
  
 `cr2`  
 Diğer taklit rengi, genellikle açık gri (COLOR_MENU).  
  
### <a name="remarks"></a>Açıklamalar  
 Kaynak eşlem iki renk ile hedef DC çizilir ( `cr1` ve `cr2`) bit eşlem'ın arka plan değiştirme Damalı düzeni. Kaynak eşlem arka planı beyaz piksel ve bit eşlem sol üst köşesindeki piksel rengi eşleşen tüm piksel olarak tanımlanır.  
  
 ![Titremeli ve özgün simgesi sürümlerinin karşılaştırması](../../mfc/reference/media/vcditheredbitmap.gif "vcditheredbitmap")  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#190](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_3.cpp)]  

### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwin.h  


##  <a name="afxgetditheredbitmap"></a>  AfxGetDitheredBitmap  
 Arka plan Titremeli (denetleyicisi) deseni ile değiştirme bir bit eşlem kopyalar.  
  
```   
void AFXAPI AfxGetDitheredBitmap(
    const CBitmap& rSrc,  
    CBitmap* pDest,  
    COLORREF cr1  ,  
    COLORREF cr2); 
```  
  
### <a name="parameters"></a>Parametreler  
 `rSrc`  
 Kaynak bitmap.  
  
 `pDest`  
 Hedef bitmap.  
  
 `cr1`  
 Genellikle iki taklit renkleri birini beyaz.  
  
 `cr2`  
 Diğer taklit rengi, genellikle açık gri (COLOR_MENU).  
  
### <a name="remarks"></a>Açıklamalar  
 Kaynak eşlem iki rengi hedef bit eşlem kopyalanır ( `cr1` ve `cr2`) kaynak bitmap ait arka plan değiştirme Damalı düzeni. Kaynak eşlem arka planı beyaz piksel ve bit eşlem sol üst köşesindeki piksel rengi eşleşen tüm piksel olarak tanımlanır.  
  
 ![Titremeli ve özgün simgesi sürümlerinin karşılaştırması](../../mfc/reference/media/vcditheredbitmap.gif "vcditheredbitmap")  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#192](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_4.cpp)]  

### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwin.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md)
