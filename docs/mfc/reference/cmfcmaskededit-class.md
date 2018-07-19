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
ms.openlocfilehash: 3b903946a2e907b67d70e5008bff602670f1751e
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/05/2018
ms.locfileid: "37849477"
---
# <a name="cmfcmaskededit-class"></a>CMFCMaskedEdit sınıfı
`CMFCMaskedEdit` Sınıfı, kullanıcı girişini maskeye doğrulayan ve doğrulanmış sonuçları bir şablona göre görüntüleyen maskelenmiş düzenleme denetimini destekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCMaskedEdit : public CEdit  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`CMFCMaskedEdit::CMFCMaskedEdit`|Varsayılan Oluşturucu.|  
|`CMFCMaskedEdit::~CMFCMaskedEdit`|Yıkıcı.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCMaskedEdit::DisableMask](#disablemask)|Kullanıcı girişini doğrulama devre dışı bırakır.|  
|[CMFCMaskedEdit::EnableGetMaskedCharsOnly](#enablegetmaskedcharsonly)|Belirtir olup olmadığını `GetWindowText` yöntemi yalnızca maskelenmiş karakterleri alır.|  
|[CMFCMaskedEdit::EnableMask](#enablemask)|Başlatır maskeli düzen denetimi.|  
|[CMFCMaskedEdit::EnableSelectByGroup](#enableselectbygroup)|Maskeli düzen denetimi, kullanıcı girişi ya da tüm kullanıcı girişi belirli grupları seçip seçmediğini belirtir.|  
|[CMFCMaskedEdit::EnableSetMaskedCharsOnly](#enablesetmaskedcharsonly)|Karakter maskelenmiş yalnızca metin doğrulanır olup olmadığını veya tam maske karşı belirtir.|  
|`CMFCMaskedEdit::GetThisClass`|Bir işaretçi alma için framework tarafından kullanılan [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) bu sınıfı türü ile ilişkilendirilmiş nesne.|  
|[CMFCMaskedEdit::GetWindowText](#getwindowtext)|Maskeli düzen denetimi metni alır doğrulandı.|  
|[CMFCMaskedEdit::SetValidChars](#setvalidchars)|Kullanıcının girebileceği geçerli karakterden oluşan bir dize belirtir.|  
|[CMFCMaskedEdit::SetWindowText](#setwindowtext)|Maskeli düzen denetimi bir istem görüntüler.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCMaskedEdit::IsMaskedChar](#ismaskedchar)|Belirtilen karakterin maskesini karaktere karşılık gelen karşı doğrulamak için framework tarafından çağırılır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanmak için aşağıdaki adımları gerçekleştirin `CMFCMaskedEdit` uygulamanızdaki denetimi:  
  
 1. Ekleme bir `CMFCMaskedEdit` penceresi sınıfınıza nesnesine.  
  
 2. Çağrı [CMFCMaskedEdit::EnableMask](#enablemask) maske belirtmek için yöntemi.  
  
 3. Çağrı [CMFCMaskedEdit::SetValidChars](#setvalidchars) geçerli karakterler listesini belirtmek için yöntemi.  
  
 4. Çağrı [CMFCMaskedEdit::SetWindowText](#setwindowtext) maskeli düzen denetimi varsayılan metni belirtmek için yöntemi.  
  
 5. Çağrı [CMFCMaskedEdit::GetWindowText](#getwindowtext) doğrulanmış metnini almak için yöntemi.  
  
 Maske, geçerli karakterler ve varsayılan metin başlatmak için bir veya daha fazla yöntemi çağırmayın, maskeli düzen denetimi yalnızca standart düzenleme denetiminin davranışını gibi davranır.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte maske (örneğin bir telefon numarası) kullanarak ayarlamak gösterilmiştir `EnableMask` maskeli düzen denetimi, maske oluşturmak için gereken yöntemini `SetValidChars` yanısırakullanıcınıngirebileceğigeçerlikarakterdizesinibelirtmekiçinyöntemi`SetWindowText` maskelenmiş bir komut istemi görüntülenecek yöntemi düzenleme denetimi. Bu örneğin parçasıdır [yeni denetimler örnek](../../visual-cpp-samples.md).  
  
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
 Kullanıcı girdisi doğrulama devre dışıysa, Maskelenmiş Düzenleme denetiminin denetim standart düzenleme gibi davranır.  
  
##  <a name="enablegetmaskedcharsonly"></a>  CMFCMaskedEdit::EnableGetMaskedCharsOnly  
 Belirtir olup olmadığını `GetWindowText` yöntemi yalnızca maskelenmiş karakterleri alır.  
  
```  
void EnableGetMaskedCharsOnly(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bSistemlerde*  
 Belirtmek için TRUE [CMFCMaskedEdit::GetWindowText](#getwindowtext) yöntemi almak yalnızca karakter; maskelenen FALSE yöntemi tam metin aldığını belirtir. Varsayılan değer True'dur.  
  
### <a name="remarks"></a>Açıklamalar  
 Maskeli karakterlerini alma etkinleştirmek için bu yöntemi kullanın. Ardından telefon numarası gibi (425) 555-0187 karşılık gelen bir maskeli düzen denetimi oluşturun. Eğer `GetWindowText` yöntemi döndürür "4255550187". Maskeli karakterlerini alma devre dışı bırakırsanız `GetWindowText` yöntemi düzenleme denetiminin, örneğin "(425) 555-0187" görüntülenen metni döndürür.  
  
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
 [in] *lpszMask*  
 Kullanıcı girişi her konumda görünebilir karakter türünü belirtir ve maske dizesini. Uzunluğunu *lpszInputTemplate* ve *lpszMask* parametresi dizeleri aynı olmalıdır. Maske karakterler hakkında daha fazla ayrıntı için Açıklamalar bölümüne bakın.  
  
 [in] *lpszInputTemplate*  
 Karakter değişmez değeri belirten bir maske şablon dize kullanıcı girişi her konumda görünür. Alt çizgi karakteri ('_') karakteri yer tutucu olarak kullanın. Uzunluğunu *lpszInputTemplate* ve *lpszMask* parametresi dizeleri aynı olmalıdır.  
  
 [in] *chMaskInputTemplate*  
 Kullanıcı girişi geçersiz her karakter için framework yerini alır ve varsayılan karakter. Bu parametrenin varsayılan değeri, alt çizgi ('_') ' dir.  
  
 [in] *lpszValid*  
 Geçerli karakter kümesini içeren bir dize. NULL, tüm karakterlerin geçerli olduğunu gösterir. Bu parametrenin varsayılan değeri null.  
  
### <a name="remarks"></a>Açıklamalar  
 Maske maskeli düzen denetimi oluşturmak için bu yöntemi kullanın. Öğesinden bir sınıf türetin `CMFCMaskedEdit` sınıf ve geçersiz kılma [CMFCMaskedEdit::IsMaskedChar](#ismaskedchar) kendi kodunuzu özel maskesi işleme için kullanılan yöntem.  
  
 Aşağıdaki tabloda, varsayılan maskesi karakterleri listeleyin:  
  
|Maskeleme karakteri|Tanım|  
|--------------------|----------------|  
|D|Basamak.|  
|d|Sayı veya boşluk.|  
|+|Artı ('+ '), eksi ('-'), veya boşluk.|  
|C|Alfabetik karakter.|  
|c|Alfabetik bir karakter veya boşluk.|  
|BİR|Alfasayısal karakter.|  
|a|Alfasayısal bir karakter veya boşluk.|  
|*|Yazdırılabilir bir karakter.|  
  
##  <a name="enableselectbygroup"></a>  CMFCMaskedEdit::EnableSelectByGroup  
 Maskeli düzen denetimi giriş belirli grupları seçin veya tüm giriş kullanıcıya izin verip vermediğini belirtir.  
  
```  
void EnableSelectByGroup(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bSistemlerde*  
 Yalnızca grupları seçmek için TRUE; Tüm metni seçmek için FALSE. Varsayılan değer True'dur.  
  
### <a name="remarks"></a>Açıklamalar  
 Maskeli düzen denetimi, bir kullanıcı grubu ya da tüm metni seçmek izin verip vermeyeceğini belirtmek için bu işlevi kullanın.  
  
 Varsayılan olarak, Grup seçerek etkindir. Bu durumda kullanıcının, yalnızca geçerli karakterleri sürekli grupları seçebilirsiniz.  
  
 Örneğin, bir telefon numarası doğrulamak için aşağıdaki maskeli düzen denetimi kullanabilirsiniz:  
  
 `m_wndMaskEdit.EnableMask(`  
  
 `_T(" ddd  ddd dddd"),// Mask string`  
  
 `_T("(___) ___-____"),// Template string`  
  
 `_T(' '));// Default char`  
  
 `m_wndMaskEdit.SetValidChars(NULL); // All characters are valid.`  
  
 `m_wndMaskEdit.SetWindowText(_T("(425) 555-0187")); // Prompt`  
  
 Grup Seçimi etkinleştirilirse, kullanıcının yalnızca "425", "555" veya "0187" dize grupları alabilirsiniz. Grup Seçimi devre dışı bırakılırsa kullanıcı telefon numarasının bütün metni alabilirsiniz: "(425) 555-0187".  
  
##  <a name="enablesetmaskedcharsonly"></a>  CMFCMaskedEdit::EnableSetMaskedCharsOnly  
 Belirten metin yalnızca maskelenmiş karakterler karşı veya tüm maskesi karşı doğrulanır.  
  
```  
void EnableSetMaskedCharsOnly(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bSistemlerde*  
 Kullanıcı karakter maskelenmiş yalnızca girişi karşı doğrulamak için TRUE; Tüm maske karşı doğrulamak için FALSE. Varsayılan değer True'dur.  
  
##  <a name="getwindowtext"></a>  CMFCMaskedEdit::GetWindowText  
 Maskeli düzen denetimi metni alır doğrulandı.  
  
```  
int GetWindowText(
    LPTSTR lpszStringBuf,  
    int nMaxCount) const;  
  
void GetWindowText(CString& rstrString) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [out] *lpszStringBuf*  
 Metin düzenleme denetiminden alan arabellek için işaretçi.  
  
 [in] *nMaxCount*  
 Almak için karakter sayısı.  
  
 [out] *rstrString*  
 Metin düzenleme denetiminden alan dize nesnesine bir başvuru.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk yöntem aşırı yüklemesi kopyalanır dizesinin bayt sayısını döndürür *lpszStringBuf* parametre arabelleği; Maskelenmiş Düzenleme denetiminin metin sahipse 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem için Maskelenmiş Düzenleme denetiminin metin kopyalar *lpszStringBuf* arabellek veya *rstrString* dize.  
  
 Bu yöntem'ı yeniden tanımladığı [CWnd::GetWindowText](../../mfc/reference/cwnd-class.md#getwindowtext).  
  
##  <a name="ismaskedchar"></a>  CMFCMaskedEdit::IsMaskedChar  
 Belirtilen karakterin maskesini karaktere karşılık gelen karşı doğrulamak için framework tarafından çağırılır.  
  
```  
virtual BOOL IsMaskedChar(
    TCHAR chChar,  
    TCHAR chMaskChar) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *chChar*  
 Doğrulanacak karakter.  
  
 [in] *chMaskChar*  
 Maske dizesini karşılık gelen karakter.  
  
### <a name="return-value"></a>Dönüş Değeri  
 TRUE ise *chChar* parametresi tarafından izin verilen karakter türüdür *chMaskChar* parametre; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Kendi giriş karakter doğrulamak için bu yöntemi yok sayın. Maske karakterler hakkında daha fazla bilgi için bkz. [CMFCMaskedEdit::EnableMask](#enablemask) yöntemi.  
  
##  <a name="setvalidchars"></a>  CMFCMaskedEdit::SetValidChars  
 Kullanıcının girebileceği geçerli karakterden oluşan bir dize belirtir.  
  
```  
void SetValidChars(LPCTSTR lpszValid=NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *lpszValid*  
 Geçerli giriş karakter kümesini içeren bir dize. NULL tüm karakterlerin geçerli olduğu anlamına gelir. Bu parametrenin varsayılan değeri null.  
  
### <a name="remarks"></a>Açıklamalar  
 Geçerli karakterler listesini tanımlamak için bu yöntemi kullanın. Bir girdi karakteri bu listede değilse, maskeli düzen denetimi bunu kabul etmez.  
  
 Aşağıdaki kod örneği yalnızca onaltılık sayı kabul eder.  
  
 `//Mask: 0xFFFFm_wndMaskEdit.EnableMask( _T(" AAAA"),                // The mask string. _T("0x____"),               // The literal template string. _T('_'));                   // The default character that replaces the backspace character.// Valid string charactersm_wndMaskEdit.SetValidChars(_T("1234567890ABCDEFabcdef"));m_wndMaskEdit.SetWindowText(_T("0x01AF"));`  
  
##  <a name="setwindowtext"></a>  CMFCMaskedEdit::SetWindowText  
 Maskeli düzen denetimi bir istem görüntüler.  
  
```  
void SetWindowText(LPCTSTR lpszString);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *lpszString*  
 Bir bilgi istemi olarak kullanılacak bir boş sonlandırılmış dizeye işaret eder.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, Denetim metin ayarlar.  
  
 Bu yöntem'ı yeniden tanımladığı [CWnd::SetWindowText](../../mfc/reference/cwnd-class.md#setwindowtext).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CEdit Sınıfı](../../mfc/reference/cedit-class.md)
