---
title: CMFCMaskedEdit Sınıfı
ms.date: 11/04/2016
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
ms.openlocfilehash: de28b308ec235e33e39aabd707677f4e75320b0b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365290"
---
# <a name="cmfcmaskededit-class"></a>CMFCMaskedEdit Sınıfı

Sınıf, `CMFCMaskedEdit` maskeye karşı kullanıcı girişini doğrulayan ve doğrulanmış sonuçları şablona göre görüntüleyen maskeli bir denetimi destekler.

## <a name="syntax"></a>Sözdizimi

```
class CMFCMaskedEdit : public CEdit
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|`CMFCMaskedEdit::CMFCMaskedEdit`|Varsayılan oluşturucu.|
|`CMFCMaskedEdit::~CMFCMaskedEdit`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCMaskedEdit::DisableMask](#disablemask)|Kullanıcı girişini doğrulayan devre dışı bırak.|
|[CMFCMaskedEdit::EnableGetMaskedCharsOnly](#enablegetmaskedcharsonly)|Yöntemin `GetWindowText` yalnızca maskeli karakterleri alıp almadığını belirtir.|
|[CMFCMaskedEdit::EnableMask](#enablemask)|Maskeli edit denetimini başolarak karşılar.|
|[CMFCMaskedEdit::EnableSelectByGroup](#enableselectbygroup)|Maskeli edit denetiminin belirli kullanıcı giriş gruplarını mı yoksa tüm kullanıcı girişlerini mi seçtiğini belirtir.|
|[CMFCMaskedEdit::EnableSetMaskedCharsOnly](#enablesetmaskedcharsonly)|Metnin yalnızca maskeli karakterlere veya tüm maskeye karşı doğrulanıp doğrulanmadığını belirtir.|
|`CMFCMaskedEdit::GetThisClass`|Bu sınıf türüyle ilişkili [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) nesnesine işaretçi almak için çerçeve tarafından kullanılır.|
|[CMFCMaskedEdit::GetWindowText](#getwindowtext)|Maskeli edit denetiminden doğrulanmış metni alır.|
|[CMFCMaskedEdit::SetValidChars](#setvalidchars)|Kullanıcının girebileceği geçerli karakter dizisini belirtir.|
|[CMFCMaskedEdit::SetWindowText](#setwindowtext)|Maskeli edit denetiminde bir istem görüntüler.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCMaskedEdit::IsMaskedChar](#ismaskedchar)|Belirtilen karakteri karşılık gelen maske karakterine karşı doğrulamak için çerçeve tarafından çağrılır.|

## <a name="remarks"></a>Açıklamalar

Uygulamanızdaki `CMFCMaskedEdit` denetimi kullanmak için aşağıdaki adımları gerçekleştirin:

1. Pencere sınıfınıza bir `CMFCMaskedEdit` nesne gömün.

2. MASKEYI belirtmek için [CMFCMaskedEdit'i arayın::Maskeyi](#enablemask) belirtmek için Maskeyi Etkinleştirme yöntemi.

3. Geçerli karakterlerin listesini belirtmek için [CMFCMaskedEdit::SetValidChars](#setvalidchars) yöntemini arayın.

4. [CMFCMaskedEdit'i arayın::Maskeli](#setwindowtext) edit denetimi için varsayılan metni belirtmek için SetWindowText yöntemini ayarlayın.

5. Doğrulanan metni almak için [CMFCMaskedEdit::GetWindowText](#getwindowtext) yöntemini arayın.

Maskeyi, geçerli karakterleri ve varsayılan metni başlatmak için bir veya daha fazla yöntem çağırmazsanız, maskeli edit denetimi standart denetim in izettiği gibi olur.

## <a name="example"></a>Örnek

Aşağıdaki örnek, maskeli düzenleme denetimi için maske oluşturmak için `EnableMask` yöntemi kullanarak bir maske (örneğin bir telefon numarası) kurmak için nasıl, kullanıcı girebilirsiniz geçerli karakter dizisi belirtmek için `SetValidChars` yöntem ve `SetWindowText` maskeli düzenleme denetiminde bir istemi görüntülemek için yöntem gösterir. Bu örnek, [Yeni Denetimler örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_NewControls#11](../../mfc/reference/codesnippet/cpp/cmfcmaskededit-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#12](../../mfc/reference/codesnippet/cpp/cmfcmaskededit-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[Cedit](../../mfc/reference/cedit-class.md)

[CMFCMaskedEdit](../../mfc/reference/cmfcmaskededit-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxmaskededit.h

## <a name="cmfcmaskededitdisablemask"></a><a name="disablemask"></a>CMFCMaskedEdit::DisableMask

Kullanıcı girişini doğrulayan devre dışı bırak.

```
void DisableMask();
```

### <a name="remarks"></a>Açıklamalar

Kullanıcı girişi doğrulaması devre dışı bırakılırsa, maskeli edit denetimi standart denetim gibi olur.

## <a name="cmfcmaskededitenablegetmaskedcharsonly"></a><a name="enablegetmaskedcharsonly"></a>CMFCMaskedEdit::EnableGetMaskedCharsOnly

Yöntemin `GetWindowText` yalnızca maskeli karakterleri alıp almadığını belirtir.

```
void EnableGetMaskedCharsOnly(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Parametreler

*bEtkinleştir*<br/>
[içinde] [CMFCMaskedEdit::GetWindowText](#getwindowtext) yönteminin yalnızca maskeli karakterleri aldığını belirtmek için DOĞRU; YÖNTEMin metnin tamamını aldığını belirtmek için FALSE. Varsayılan değer TRUE'dur.

### <a name="remarks"></a>Açıklamalar

Maskeli karakterleri almak için bu yöntemi kullanın. Ardından (425) 555-0187 gibi telefon numarasına karşılık gelen maskeli bir denetim oluşturun. `GetWindowText` Yöntemi ararsanız, "4255550187" döndürür. Maskeli karakterleri alma devre dışı ederseniz, `GetWindowText` yöntem "(425) 555-0187" gibi edinme denetiminde görüntülenen metni döndürür.

## <a name="cmfcmaskededitenablemask"></a><a name="enablemask"></a>CMFCMaskedEdit::EnableMask

Maskeli edit denetimini başolarak karşılar.

```
void EnableMask(
    LPCTSTR lpszMask,
    LPCTSTR lpszInputTemplate,
    TCHAR chMaskInputTemplate=_T('_'),
    LPCTSTR lpszValid=NULL);
```

### <a name="parameters"></a>Parametreler

*lpszMask*<br/>
[içinde] Kullanıcı girişindeki her konumda görünebilecek karakter türünü belirten bir maske dizesi. *lpszInputTemplate* ve *lpszMask* parametre dizelerinin uzunluğu aynı olmalıdır. Maske karakterleri hakkında daha fazla ayrıntı için Açıklamalar bölümüne bakın.

*lpszInputTemplate*<br/>
[içinde] Kullanıcı girişindeki her konumda görünebilecek gerçek karakterleri belirten bir maske şablon udizesi. Alt alt karakter ('_') karakter yer tutucusu olarak kullanın. *lpszInputTemplate* ve *lpszMask* parametre dizelerinin uzunluğu aynı olmalıdır.

*chMaskInputTemplate*<br/>
[içinde] Çerçevenin kullanıcı girişindeki her geçersiz karakter için yerine koyduğu varsayılan bir karakter. Bu parametrenin varsayılan değeri alt ('_') olarak altı çizilir.

*lpszValid*<br/>
[içinde] Geçerli karakter kümesi içeren bir dize. NULL tüm karakterlerin geçerli olduğunu gösterir. Bu parametrenin varsayılan değeri NULL'dur.

### <a name="remarks"></a>Açıklamalar

Maskeli edit denetimi için maskeoluşturmak için bu yöntemi kullanın. Sınıftan `CMFCMaskedEdit` bir sınıf türetin ve [CMFCMaskedEdit geçersiz kılın::Özel](#ismaskedchar) maske işleme için kendi kodunuzu kullanmak için IsMaskedChar yöntemi.

Aşağıdaki tabloda varsayılan maske karakterleri listele:

|Maske Karakteri|Tanım|
|--------------------|----------------|
|D|Basamak.|
|d|Basamak veya boşluk.|
|+|Artı ('+'), eksi ('-'), veya boşluk.|
|C|Alfabetik karakter.|
|c|Alfabetik karakter veya boşluk.|
|A|Alfanümerik karakter.|
|a|Alfasayısal karakter veya boşluk.|
|*|Yazdırılabilir bir karakter.|

## <a name="cmfcmaskededitenableselectbygroup"></a><a name="enableselectbygroup"></a>CMFCMaskedEdit::EnableSelectByGroup

Maskeli edit denetiminin, kullanıcının belirli grupları veya tüm girişi seçmesine izin verip vermediği belirtilir.

```
void EnableSelectByGroup(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Parametreler

*bEtkinleştir*<br/>
[içinde] Yalnızca grupları seçmek için DOĞRU; Metnin tamamını seçmek için FALSE. Varsayılan değer TRUE'dur.

### <a name="remarks"></a>Açıklamalar

Maskeli düzenleme denetiminin kullanıcının gruba mı yoksa metnin tamamına mı göre seçim yapmasına izin verdiğini belirtmek için bu işlevi kullanın.

Varsayılan olarak, gruba göre seçim etkinleştirilir. Bu durumda, kullanıcı yalnızca sürekli geçerli karakter grupları seçebilir.

Örneğin, bir telefon numarasını doğrulamak için aşağıdaki maskeli denetim denetimini kullanabilirsiniz:

```cpp
m_wndMaskEdit.EnableMask(
    _T(" ddd  ddd dddd"),  // Mask string
    _T("(___) ___-____"),  // Template string
    _T(' '));              // Default char

m_wndMaskEdit.SetValidChars(NULL); // All characters are valid.

m_wndMaskEdit.SetWindowText(_T("(425) 555-0187")); // Prompt
```

Gruba göre seçim etkinse, kullanıcı yalnızca "425", "555" veya "0187" dize gruplarını alabilir. Grup seçimi devre dışı bırakılırsa, kullanıcı telefon numarasının tüm metnini alabilir: "(425) 555-0187".

## <a name="cmfcmaskededitenablesetmaskedcharsonly"></a><a name="enablesetmaskedcharsonly"></a>CMFCMaskedEdit::EnableSetMaskedCharsOnly

Metnin yalnızca maskeli karakterlere veya tüm maskeye karşı doğrulanıp doğrulanmadığını belirtir.

```
void EnableSetMaskedCharsOnly(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Parametreler

*bEtkinleştir*<br/>
[içinde] Yalnızca maskeli karakterlere karşı kullanıcı girişini doğrulamak için TRUE; TÜM maskekarşı doğrulamak için YANLIŞ. Varsayılan değer TRUE'dur.

## <a name="cmfcmaskededitgetwindowtext"></a><a name="getwindowtext"></a>CMFCMaskedEdit::GetWindowText

Maskeli edit denetiminden doğrulanmış metni alır.

```
int GetWindowText(
    LPTSTR lpszStringBuf,
    int nMaxCount) const;

void GetWindowText(CString& rstrString) const;
```

### <a name="parameters"></a>Parametreler

*lpszStringBuf*<br/>
[çıkış] Metni denetimden alan arabelleğe işaretçi.

*nMaxCount*<br/>
[içinde] Alınacak maksimum karakter sayısı.

*rstrString*<br/>
[çıkış] Metni denetimden alan dize nesnesine yapılan başvuru.

### <a name="return-value"></a>Dönüş Değeri

İlk yöntem aşırı *lpszStringBuf* parametre arabelleği kopyalanır dize bayt sayısını döndürür; 0 maskeli edit denetimi hiçbir metin varsa.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, metni maskeli edit denetiminden *lpszStringBuf* arabelleği veya *rstrString* dizesine kopyalar.

Bu yöntem [CWnd yeniden tanımlar::GetWindowText](../../mfc/reference/cwnd-class.md#getwindowtext).

## <a name="cmfcmaskededitismaskedchar"></a><a name="ismaskedchar"></a>CMFCMaskedEdit::IsMaskedChar

Belirtilen karakteri karşılık gelen maske karakterine karşı doğrulamak için çerçeve tarafından çağrılır.

```
virtual BOOL IsMaskedChar(
    TCHAR chChar,
    TCHAR chMaskChar) const;
```

### <a name="parameters"></a>Parametreler

*chChar*<br/>
[içinde] Doğrulanacak karakter.

*chMaskChar*<br/>
[içinde] Maske dizesinden karşılık gelen karakter.

### <a name="return-value"></a>Dönüş Değeri

*CHChar* parametresi *chMaskChar* parametresi tarafından izin verilen karakter türü ise DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Giriş karakterlerini kendi olarak doğrulamak için bu yöntemi geçersiz kılın. Maske karakterleri hakkında daha fazla bilgi için [CMFCMaskedEdit::EnableMask](#enablemask) yöntemine bakın.

## <a name="cmfcmaskededitsetvalidchars"></a><a name="setvalidchars"></a>CMFCMaskedEdit::SetValidChars

Kullanıcının girebileceği geçerli karakter dizisini belirtir.

```
void SetValidChars(LPCTSTR lpszValid=NULL);
```

### <a name="parameters"></a>Parametreler

*lpszValid*<br/>
[içinde] Geçerli giriş karakterleri kümesini içeren bir dize. NULL, tüm karakterlerin geçerli olduğu anlamına gelir. Bu parametrenin varsayılan değeri NULL'dur.

### <a name="remarks"></a>Açıklamalar

Geçerli karakterlerin listesini tanımlamak için bu yöntemi kullanın. Bu listede bir giriş karakteri yoksa, maskeli edit denetimi bunu kabul etmez.

Aşağıdaki kod örneği yalnızca hexadecimal sayıları kabul eder.

```cpp
//Mask: 0xFFFF
m_wndMaskEdit.EnableMask(
    _T(" AAAA"),                // The mask string.
    _T("0x____"),               // The literal template string.
    _T('_'));                   // The default character that
                                // replaces the backspace character.
// Valid string characters
m_wndMaskEdit.SetValidChars(_T("1234567890ABCDEFabcdef"));m_wndMaskEdit.SetWindowText(_T("0x01AF"));
```

## <a name="cmfcmaskededitsetwindowtext"></a><a name="setwindowtext"></a>CMFCMaskedEdit::SetWindowText

Maskeli edit denetiminde bir istem görüntüler.

```
void SetWindowText(LPCTSTR lpszString);
```

### <a name="parameters"></a>Parametreler

*lpszString*<br/>
[içinde] İstem olarak kullanılacak null-sonlandırılan dizeyi işaret edin.

### <a name="remarks"></a>Açıklamalar

Bu yöntem denetim metnini ayarlar.

Bu yöntem [CWnd yeniden tanımlar::SetWindowText](../../mfc/reference/cwnd-class.md#setwindowtext).

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CEdit Sınıfı](../../mfc/reference/cedit-class.md)
