---
title: CMFCMaskedEdit sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCMaskedEdit
- AFXMASKEDEDIT/CMFCMaskedEdit
- AFXMASKEDEDIT/CMFCMaskedEdit::DisableMask
- AFXMASKEDEDIT/CMFCMaskedEdit::EnableGetMaskedCharsOnly
- AFXMASKEDEDIT/CMFCMaskedEdit::EnableMask
- AFXMASKEDEDIT/CMFCMaskedEdit::EnableSelectByGroup
- AFXMASKEDEDIT/CMFCMaskedEdit::EnableSetMaskedCharsOnly
- AFXMASKEDEDIT/CMFCMaskedEdit::GetWindowText
- AFXMASKEDEDIT/CMFCMaskedEdit::SetValidChars
- AFXMASKEDEDIT/CMFCMaskedEdit::SetWindowText
- AFXMASKEDEDIT/CMFCMaskedEdit::IsMaskedChar
dev_langs:
- C++
helpviewer_keywords:
- CMFCMaskedEdit [MFC], DisableMask
- CMFCMaskedEdit [MFC], EnableGetMaskedCharsOnly
- CMFCMaskedEdit [MFC], EnableMask
- CMFCMaskedEdit [MFC], EnableSelectByGroup
- CMFCMaskedEdit [MFC], EnableSetMaskedCharsOnly
- CMFCMaskedEdit [MFC], GetWindowText
- CMFCMaskedEdit [MFC], SetValidChars
- CMFCMaskedEdit [MFC], SetWindowText
- CMFCMaskedEdit [MFC], IsMaskedChar
ms.assetid: 13b1a645-2d5d-4c37-8599-16d5003f23a5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 985cd4011dbb1ea8ccad7cd40c81833dd5507f11
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="cmfcmaskededit-class"></a>CMFCMaskedEdit sınıfı
`CMFCMaskedEdit` Sınıfı, kullanıcı giriş maskesi karşı doğrular ve bir şablon göre doğrulanmış sonuçları görüntüler maskeli düzenleme denetimi destekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCMaskedEdit : public CEdit  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`CMFCMaskedEdit::CMFCMaskedEdit`|Varsayılan Oluşturucu.|  
|`CMFCMaskedEdit::~CMFCMaskedEdit`|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCMaskedEdit::DisableMask](#disablemask)|Kullanıcı girişini doğrulama devre dışı bırakır.|  
|[CMFCMaskedEdit::EnableGetMaskedCharsOnly](#enablegetmaskedcharsonly)|Belirtir olup olmadığını `GetWindowText` yöntemi yalnızca maskelenmiş karakterleri alır.|  
|[CMFCMaskedEdit::EnableMask](#enablemask)|Başlatır maskeli düzen denetimi.|  
|[CMFCMaskedEdit::EnableSelectByGroup](#enableselectbygroup)|Maskeli düzenleme denetimi kullanıcı girişi ya da tüm kullanıcı girişi belirli gruplarını seçer olup olmadığını belirtir.|  
|[CMFCMaskedEdit::EnableSetMaskedCharsOnly](#enablesetmaskedcharsonly)|Karakter maskelenmiş yalnızca metin doğrulanır olup olmadığını veya tam maskesi karşı belirtir.|  
|`CMFCMaskedEdit::GetThisClass`|Bir işaretçi elde etmek için çerçevesi tarafından kullanılan [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) Bu sınıf türü ile ilişkili nesne.|  
|[CMFCMaskedEdit::GetWindowText](#getwindowtext)|Maskeli düzenleme denetimi metinden alır doğrulandı.|  
|[CMFCMaskedEdit::SetValidChars](#setvalidchars)|Bir kullanıcının girebileceği geçerli karakter dizesi belirtir.|  
|[CMFCMaskedEdit::SetWindowText](#setwindowtext)|Maskeli düzenleme denetimi bir istem görüntüler.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCMaskedEdit::IsMaskedChar](#ismaskedchar)|Belirtilen karakter karşılık gelen maskeleme karakteri karşı doğrulamak için çerçevesi tarafından çağrılır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanmak için aşağıdaki adımları gerçekleştirin `CMFCMaskedEdit` uygulamanızda denetimi:  
  
 1. Embed bir `CMFCMaskedEdit` pencere sınıfı nesnesine.  
  
 2. Çağrı [CMFCMaskedEdit::EnableMask](#enablemask) yöntemi maskesi belirtin.  
  
 3. Çağrı [CMFCMaskedEdit::SetValidChars](#setvalidchars) yöntemi geçerli karakterler listesini belirtin.  
  
 4. Çağrı [CMFCMaskedEdit::SetWindowText](#setwindowtext) yöntemi maskeli düzen denetimi için varsayılan metni belirtin.  
  
 5. Çağrı [CMFCMaskedEdit::GetWindowText](#getwindowtext) doğrulanmış metin alma yöntemi.  
  
 Maske, geçerli karakterler ve varsayılan metin başlatmak için bir veya daha fazla yöntemi çağırmayın, maskeli düzenleme denetimi yalnızca standart düzenleme denetimi davranır gibi davranır.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, maskesi (örneğin bir telefon numarası) kullanarak ayarlamak gösterilmiştir `EnableMask` maskeli düzen denetimi, maskesi oluşturmak için yöntemi `SetValidChars` kullanıcı girebilir geçerli karakterler ve oluşanbirdizebelirtmekiçinyöntemi`SetWindowText` bir istem maskelenmiş görüntülenecek yöntemi düzenleme denetimi. Bu örneğin parçasıdır [yeni denetimler örnek](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#11](../../mfc/reference/codesnippet/cpp/cmfcmaskededit-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#12](../../mfc/reference/codesnippet/cpp/cmfcmaskededit-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CEdit](../../mfc/reference/cedit-class.md)  
  
 [CMFCMaskedEdit](../../mfc/reference/cmfcmaskededit-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxmaskededit.h  
  
##  <a name="disablemask"></a>  CMFCMaskedEdit::DisableMask  
 Kullanıcı girişini doğrulama devre dışı bırakır.  
  
```  
void DisableMask();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanıcı girdisi doğrulama devre dışıysa, maskeli düzenleme denetimi standart düzenleme denetimi gibi davranır.  
  
##  <a name="enablegetmaskedcharsonly"></a>  CMFCMaskedEdit::EnableGetMaskedCharsOnly  
 Belirtir olup olmadığını `GetWindowText` yöntemi yalnızca maskelenmiş karakterleri alır.  
  
```  
void EnableGetMaskedCharsOnly(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `bEnable`  
 `TRUE` belirtmek için [CMFCMaskedEdit::GetWindowText](#getwindowtext) yöntemi almak yalnızca maskelenmiş karakter; `FALSE` yöntemi tüm metni almak belirtmek için. Varsayılan değer `TRUE` şeklindedir.  
  
### <a name="remarks"></a>Açıklamalar  
 Maskeli karakterlerini alma etkinleştirmek için bu yöntemi kullanın. Daha sonra (425) 555-0187 gibi telefon numarası karşılık gelen bir maskeli düzenleme denetimi oluşturun. Çağırırsanız `GetWindowText` , bu yöntem "4255550187". Maskeli karakterlerini alma devre dışı bırakırsanız `GetWindowText` yöntemi düzenleme denetimi, örneğin "(425) 555-0187" görüntülenen metni döndürür.  
  
##  <a name="enablemask"></a>  CMFCMaskedEdit::EnableMask  
 Başlatır maskeli düzen denetimi.  
  
```  
void EnableMask(
    LPCTSTR lpszMask,  
    LPCTSTR lpszInputTemplate,  
    TCHAR chMaskInputTemplate=_T('_'),  
    LPCTSTR lpszValid=NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `lpszMask`  
 Kullanıcı girişi her konumda görünebilir karakter türünü belirten bir maskesi dize. Uzunluğu `lpszInputTemplate` ve `lpszMask` parametresi dizeleri aynı olmalıdır. Maske karakterler hakkında daha fazla ayrıntı için Açıklamalar bölümüne bakın.  
  
 [in] `lpszInputTemplate`  
 Sabit karakterleri belirten maskesi şablon dizesini kullanıcı girişi her konumunda yer alabilir. Alt çizgi karakteri ('_') karakteri yer tutucu olarak kullanın. Uzunluğu `lpszInputTemplate` ve `lpszMask` parametresi dizeleri aynı olmalıdır.  
  
 [in] `chMaskInputTemplate`  
 Her kullanıcı girişi geçersiz karakter için framework değiştirir varsayılan karakter. Alt çizgi ('_') bu parametrenin varsayılan değeridir.  
  
 [in] `lpszValid`  
 Geçerli karakter kümesini içeren bir dize. `NULL` Tüm karakterlerin geçerli olduğunu gösterir. Bu parametrenin varsayılan değeri `NULL`.  
  
### <a name="remarks"></a>Açıklamalar  
 Maskeli düzenleme denetimi maske oluşturmak için bu yöntemi kullanın. Öğesinden bir sınıf türetin `CMFCMaskedEdit` sınıfı ve geçersiz kılma [CMFCMaskedEdit::IsMaskedChar](#ismaskedchar) kendi kodunuzu özel maskesi işleme için kullanılacak yöntemi.  
  
 Aşağıdaki tabloda, varsayılan maskesi karakterleri listesi:  
  
|Maskeleme karakteri|Tanım|  
|--------------------|----------------|  
|D|Sayı.|  
|d|Basamak veya aralık.|  
|+|Artı ('+ '), eksi ('-'), veya boşluk.|  
|C|Alfasayısal karakter.|  
|c|Alfabetik bir karakter veya boşluk.|  
|BİR|Alfasayısal karakter.|  
|a|Alfasayısal karakter veya boşluk.|  
|*|Yazdırılabilir karakter.|  
  
##  <a name="enableselectbygroup"></a>  CMFCMaskedEdit::EnableSelectByGroup  
 Maskeli düzenleme denetimi seçilen belirli grupların giriş ya da tüm giriş kullanıcıya izin verip vermeyeceğini belirtir.  
  
```  
void EnableSelectByGroup(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `bEnable`  
 `TRUE` yalnızca grupları seçmek için; `FALSE` tüm metni seçmek için. Varsayılan değer `TRUE` şeklindedir.  
  
### <a name="remarks"></a>Açıklamalar  
 Maskeli düzenleme denetimi grubu veya tüm metni seçmek bir kullanıcı izin verip vermediğini belirtmek için bu işlevi kullanın.  
  
 Varsayılan olarak, grup tarafından seçimi etkinleştirilir. Bu durumda kullanıcının geçerli karakterler yalnızca sürekli grupları seçebilirsiniz.  
  
 Örneğin, bir telefon numarasını doğrulamak için aşağıdaki maskeli düzenleme denetimi kullanabilirsiniz:  
  
 `m_wndMaskEdit.EnableMask(`  
  
 `_T(" ddd  ddd dddd"),// Mask string`  
  
 `_T("(___) ___-____"),// Template string`  
  
 `_T(' '));// Default char`  
  
 `m_wndMaskEdit.SetValidChars(NULL); // All characters are valid.`  
  
 `m_wndMaskEdit.SetWindowText(_T("(425) 555-0187")); // Prompt`  
  
 Grup Seçimi etkinleştirilirse, kullanıcının yalnızca "425", "555" veya "0187" dizesi grupları alabilir. Grup Seçimi devre dışı bırakılmışsa kullanıcı telefon numarasını tüm metnin alabilirsiniz: "(425) 555-0187".  
  
##  <a name="enablesetmaskedcharsonly"></a>  CMFCMaskedEdit::EnableSetMaskedCharsOnly  
 Belirtir metin yalnızca maskelenmiş karakterleri karşı ya da tüm maskesi karşı doğrulanır.  
  
```  
void EnableSetMaskedCharsOnly(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `bEnable`  
 `TRUE` kullanıcıyı doğrulamak için giriş karşı yalnızca karakter maskelenmiş; `FALSE` karşı tüm maskesi doğrulanamadı. Varsayılan değer `TRUE` şeklindedir.  
  
##  <a name="getwindowtext"></a>  CMFCMaskedEdit::GetWindowText  
 Maskeli düzenleme denetimi metinden alır doğrulandı.  
  
```  
int GetWindowText(
    LPTSTR lpszStringBuf,  
    int nMaxCount) const;  
  
void GetWindowText(CString& rstrString) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [out] `lpszStringBuf`  
 Metin düzenleme denetiminden alan bir arabellek için bir işaretçi.  
  
 [in] `nMaxCount`  
 Karakter almak için maksimum sayısı.  
  
 [out] `rstrString`  
 Düzenleme denetiminden metni alır dize nesnesine başvuru.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk yöntemi aşırı yüklemesini kopyalanır dizesinin bayt sayısını verir `lpszStringBuf` parametre arabelleği; maskeli düzenleme denetimi metin sahipse 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem maskeli düzenleme denetimi metni kopyalar `lpszStringBuf` arabellek veya `rstrString` dize.  
  
 Bu yöntem yeniden tanımlamaktadır [CWnd::GetWindowText](../../mfc/reference/cwnd-class.md#getwindowtext).  
  
##  <a name="ismaskedchar"></a>  CMFCMaskedEdit::IsMaskedChar  
 Belirtilen karakter karşılık gelen maskeleme karakteri karşı doğrulamak için çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL IsMaskedChar(
    TCHAR chChar,  
    TCHAR chMaskChar) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `chChar`  
 Doğrulanacak karakter.  
  
 [in] `chMaskChar`  
 Maske dizesini karşılık gelen karakter.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` varsa `chChar` parametredir tarafından izin verilen karakter türü `chMaskChar` parametresi; Aksi halde, `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Kendi giriş karakter doğrulamak için bu yöntemi geçersiz kılın. Maske karakterler hakkında daha fazla bilgi için bkz: [CMFCMaskedEdit::EnableMask](#enablemask) yöntemi.  
  
##  <a name="setvalidchars"></a>  CMFCMaskedEdit::SetValidChars  
 Bir kullanıcının girebileceği geçerli karakter dizesi belirtir.  
  
```  
void SetValidChars(LPCTSTR lpszValid=NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `lpszValid`  
 Geçerli giriş karakter kümesi içeren bir dize. `NULL` Tüm karakterlerin geçerli olduğunu anlamına gelir. Bu parametrenin varsayılan değeri `NULL`.  
  
### <a name="remarks"></a>Açıklamalar  
 Geçerli karakterler listesini tanımlamak için bu yöntemi kullanın. Bir giriş karakter bu listede değilse, maskeli düzenleme denetimi bunu kabul etmez.  
  
 Aşağıdaki kod örneği yalnızca onaltılık sayıları kabul eder.  
  
 `//Mask: 0xFFFFm_wndMaskEdit.EnableMask( _T(" AAAA"),                // The mask string. _T("0x____"),               // The literal template string. _T('_'));                   // The default character that replaces the backspace character.// Valid string charactersm_wndMaskEdit.SetValidChars(_T("1234567890ABCDEFabcdef"));m_wndMaskEdit.SetWindowText(_T("0x01AF"));`  
  
##  <a name="setwindowtext"></a>  CMFCMaskedEdit::SetWindowText  
 Maskeli düzenleme denetimi bir istem görüntüler.  
  
```  
void SetWindowText(LPCTSTR lpszString);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `lpszString`  
 Bir bilgi istemi olarak kullanılacak null ile sonlandırılmış bir dize noktalarına.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem kontrol metni ayarlar.  
  
 Bu yöntem yeniden tanımlamaktadır [CWnd::SetWindowText](../../mfc/reference/cwnd-class.md#setwindowtext).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CEdit Sınıfı](../../mfc/reference/cedit-class.md)
