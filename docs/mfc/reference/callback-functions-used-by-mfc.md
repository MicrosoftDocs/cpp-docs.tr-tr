---
title: "MFC tarafından kullanılan geri çağırma işlevleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.mfc.functions
dev_langs: C++
helpviewer_keywords:
- callback functions [MFC], MFC
- MFC, callback functions
- functions [MFC], callback
- callback functions [MFC]
ms.assetid: b2a6857c-fdd3-45ec-8fd8-2e71fac77582
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4c25693b31359b70ba36fd43394b7074e464c954
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="callback-functions-used-by-mfc"></a>MFC Tarafından Kullanılan Geri Çağırma İşlevleri
Üç geri arama işlevleri Microsoft Foundation Class Kitaplığı'nda görünür. Bu geri çağırma işlevleri geçirilecek [CDC::EnumObjects](../../mfc/reference/cdc-class.md#enumobjects), [CDC::GrayString](../../mfc/reference/cdc-class.md#graystring), ve [CDC::SetAbortProc](../../mfc/reference/cdc-class.md#setabortproc). Tüm geri arama işlevleri MFC Windows için geri çağırma sınırlarında durumlar olamaz bu yana döndürmeden önce yakalamak gerekir olduğunu unutmayın. Özel durumlar hakkında daha fazla bilgi için bkz: [özel durumları](../../mfc/exception-handling-in-mfc.md).  

|Ad||  
|----------|-----------------|  
|[CDC::EnumObjects için geri çağırma işlevi](#enum_objects)||  
|[CDC::GrayString için geri çağırma işlevi](#graystring)||
|[CDC::SetAbortProc için geri çağırma işlevi](#setabortproc)|| 

## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwin.h 

## <a name="enum_objects"></a>CDC::EnumObjects için geri çağırma işlevi
*ObjectFunc* adı uygulama tarafından sağlanan işlev adı için bir yer tutucudur.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
int CALLBACK EXPORT ObjectFunc(
    LPSTR lpszLogObject,  
    LPSTR* lpData);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpszLogObject*  
 İşaret eden bir [LOGPEN](../../mfc/reference/logpen-structure.md) veya [LOGBRUSH](../../mfc/reference/logbrush-structure.md) nesnenin mantıksal öznitelikleri hakkında bilgi içeren veri yapısı.  
  
 `lpData`  
 Uygulama tarafından sağlanan veri noktalarına geçirilen `EnumObjects` işlevi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geri çağırma işlevi döndüren bir `int`. Bu dönüş değeri, kullanıcı tanımlı ' dir. Geri çağırma işlevi 0, döndürürse `EnumObjects` erken numaralandırması durdurur.  
  
### <a name="remarks"></a>Açıklamalar  
 Gerçek ad verilmelidir.  
  
## <a name="graystring"></a>CDC::GrayString için geri çağırma işlevi
*OutputFunc* uygulama tarafından sağlanan geri çağırma işlevi adı için bir yer tutucudur.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
BOOL CALLBACK EXPORT OutputFunc(
    HDC hDC,  
    LPARAM lpData,  
    int nCount);
```  
  
### <a name="parameters"></a>Parametreler  
 `hDC`  
 Bir bit eşlem en az ile bellek cihaz bağlamı tanımlar genişlik ve yükseklik tarafından belirtilen `nWidth` ve `nHeight` için `GrayString`.  
  
 `lpData`  
 Çizilecek karakter dizesine işaret eder.  
  
 `nCount`  
 Çıktı için karakter sayısını belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geri çağırma işlevinin dönüş değeri olmalıdır **TRUE** başarı; belirtmek için Aksi takdirde değer **FALSE**.  
  
### <a name="remarks"></a>Açıklamalar  
 Geri çağırma işlevi (*OutputFunc*) (0,0) koordinatlara göre resim çizme gerekir yerine (*x*, *y*).  

## <a name="setabortproc"></a>CDC::SetAbortProc için geri çağırma işlevi
Adı *AbortFunc* uygulama tarafından sağlanan işlev adı için bir yer tutucudur.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
BOOL CALLBACK EXPORT AbortFunc(
    HDC hPr,  
    int code);
```  
  
### <a name="parameters"></a>Parametreler  
 *hPr*  
 Cihaz bağlamı tanımlar.  
  
 `code`  
 Bir hata oluştu olup olmadığını belirtir. Herhangi bir hata oluştuysa, 0'dır. Bu **SP_OUTOFDISK** Yazdırma Yöneticisi'ni şu anda disk alanı yetersiz ise ve daha fazla disk alanı uygulama bekliyorsa kullanılabilir hale gelecektir. Varsa `code` olan **SP_OUTOFDISK**, yazdırma işi iptal etmek uygulama yok. Mevcut değilse, Yazdırma Yöneticisi çağırarak verim gerekir **PeekMessage** veya **GetMessage** Windows işlevi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Abort işleyici işlevinin dönüş değeri yazdırma işi devam etmek için ise sıfır dışında 0 ise bu iptal edildiyse.  
  
### <a name="remarks"></a>Açıklamalar  
 Gerçek adı, açıklamalar bölümünde açıklandığı gibi dışarı aktarılmalıdır [CDC::SetAbortProc](../../mfc/reference/cdc-class.md#setabortproc).  
 
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar, stiller, geri aramalar ve ileti eşlemeleri](structures-styles-callbacks-and-message-maps.md) [CDC::EnumObjects](../../mfc/reference/cdc-class.md#enumobjects) [CDC::SetAbortProc](../../mfc/reference/cdc-class.md#setabortproc) [CDC::GrayString](../../mfc/reference/cdc-class.md#graystring)

