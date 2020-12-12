---
description: 'Daha fazla bilgi edinin: CMFCMaskedEdit Class'
title: CMFCMaskedEdit sınıfı
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
ms.openlocfilehash: 7ac61240e2941eafbbac3cbb03a4884e282cbca3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97265161"
---
# <a name="cmfcmaskededit-class"></a>CMFCMaskedEdit sınıfı

`CMFCMaskedEdit`Sınıfı, bir maskeye karşı Kullanıcı girişini doğrulayan ve doğrulanan sonuçları bir şablona göre gösteren maskelenmiş bir düzenleme denetimini destekler.

## <a name="syntax"></a>Syntax

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
|[CMFCMaskedEdit::D isableMask](#disablemask)|Kullanıcı girişini doğrulamayı devre dışı bırakır.|
|[CMFCMaskedEdit::EnableGetMaskedCharsOnly](#enablegetmaskedcharsonly)|`GetWindowText`Yöntemin yalnızca maskelenmiş karakterleri alıp almadığını belirtir.|
|[CMFCMaskedEdit:: EnableMask](#enablemask)|Maskelenmiş düzenleme denetimini başlatır.|
|[CMFCMaskedEdit:: EnableSelectByGroup](#enableselectbygroup)|Maskelenmiş düzenleme denetiminin belirli kullanıcı girişi gruplarını mı yoksa tüm kullanıcı girişlerini mi seçip seçmediğini belirtir.|
|[CMFCMaskedEdit::EnableSetMaskedCharsOnly](#enablesetmaskedcharsonly)|Metnin yalnızca maskelenmiş karakterlere veya bütün maskeye karşı doğrulanıp onaylanmadığını belirtir.|
|`CMFCMaskedEdit::GetThisClass`|Bu sınıf türüyle ilişkili [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) nesnesine bir işaretçi almak için Framework tarafından kullanılır.|
|[CMFCMaskedEdit:: GetWindowText](#getwindowtext)|Maskelenmiş düzenleme denetiminden doğrulanan metni alır.|
|[CMFCMaskedEdit:: SetValidChars](#setvalidchars)|Kullanıcının girebileceği geçerli karakterlerin bir dizesini belirtir.|
|[CMFCMaskedEdit:: SetWindowText](#setwindowtext)|Maskelenmiş düzenleme denetiminde bir istem görüntüler.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCMaskedEdit::IsMaskedChar](#ismaskedchar)|Belirtilen karakteri karşılık gelen maske karakteriyle doğrulamak için Framework tarafından çağırılır.|

## <a name="remarks"></a>Açıklamalar

Uygulamanızda denetimi kullanmak için aşağıdaki adımları gerçekleştirin `CMFCMaskedEdit` :

1. `CMFCMaskedEdit`Pencere sınıfınıza bir nesne ekleyin.

2. Maskeyi belirtmek için [CMFCMaskedEdit:: EnableMask](#enablemask) metodunu çağırın.

3. Geçerli karakterlerin listesini belirtmek için [CMFCMaskedEdit:: SetValidChars](#setvalidchars) metodunu çağırın.

4. Maskelenmiş düzenleme denetimi için varsayılan metni belirtmek üzere [CMFCMaskedEdit:: SetWindowText](#setwindowtext) yöntemini çağırın.

5. Doğrulanan metni almak için [CMFCMaskedEdit:: GetWindowText](#getwindowtext) yöntemini çağırın.

Maskeyi, geçerli karakterleri ve varsayılan metni başlatmak için bir veya daha fazla yöntem çağırmazkdıysanız, maskelenmiş düzenleme denetimi, standart düzenleme denetimi davrandığı gibi davranır.

## <a name="example"></a>Örnek

Aşağıdaki örnek, maskelenmiş düzenleme denetimi için bir maske oluşturmak üzere yöntemi kullanılarak bir maskenin (örneğin, bir telefon numarası) nasıl ayarlanacağını `EnableMask` , `SetValidChars` kullanıcının girebileceği geçerli karakterlerin bir dizesini belirtme yöntemini ve `SetWindowText` maskelenmiş düzenleme denetiminde bir istem görüntüleme yöntemini kullanarak gösterir. Bu örnek, [Yeni denetimler örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_NewControls#11](../../mfc/reference/codesnippet/cpp/cmfcmaskededit-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#12](../../mfc/reference/codesnippet/cpp/cmfcmaskededit-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CEdit](../../mfc/reference/cedit-class.md)

[CMFCMaskedEdit](../../mfc/reference/cmfcmaskededit-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxmaskededit. h

## <a name="cmfcmaskededitdisablemask"></a><a name="disablemask"></a> CMFCMaskedEdit::D isableMask

Kullanıcı girişini doğrulamayı devre dışı bırakır.

```cpp
void DisableMask();
```

### <a name="remarks"></a>Açıklamalar

Kullanıcı girişi doğrulaması devre dışıysa, maskelenmiş düzenleme denetimi standart düzenleme denetimi gibi davranır.

## <a name="cmfcmaskededitenablegetmaskedcharsonly"></a><a name="enablegetmaskedcharsonly"></a> CMFCMaskedEdit::EnableGetMaskedCharsOnly

`GetWindowText`Yöntemin yalnızca maskelenmiş karakterleri alıp almadığını belirtir.

```cpp
void EnableGetMaskedCharsOnly(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Parametreler

*bEnable*<br/>
'ndaki [CMFCMaskedEdit:: GetWindowText](#getwindowtext) yönteminin yalnızca maskelenmiş karakterleri aldığını BELIRTMEK için true; Metodun metnin tamamını aldığını belirtmek için FALSE. Varsayılan değer TRUE 'dur.

### <a name="remarks"></a>Açıklamalar

Maskelenmiş karakterleri almayı etkinleştirmek için bu yöntemi kullanın. Ardından, (425) 555-0187 gibi telefon numarasına karşılık gelen bir maskelenmiş düzenleme denetimi oluşturun. `GetWindowText`Yöntemini çağırırsanız, "4255550187" döndürür. Maskelenmiş karakterleri almayı devre dışı bırakırsanız, `GetWindowText` Yöntem düzenleme denetiminde görüntülenen metni döndürür, örneğin "(425) 555-0187".

## <a name="cmfcmaskededitenablemask"></a><a name="enablemask"></a> CMFCMaskedEdit:: EnableMask

Maskelenmiş düzenleme denetimini başlatır.

```cpp
void EnableMask(
    LPCTSTR lpszMask,
    LPCTSTR lpszInputTemplate,
    TCHAR chMaskInputTemplate=_T('_'),
    LPCTSTR lpszValid=NULL);
```

### <a name="parameters"></a>Parametreler

*lpszMask*<br/>
'ndaki Kullanıcı girişinde her konumda görünebilen karakter türünü belirten bir maske dizesi. *LpszInputTemplate* ve *lpszMask* parametre dizelerinin uzunluğu aynı olmalıdır. Maske karakterleri hakkında daha ayrıntılı bilgi için açıklamalar bölümüne bakın.

*lpszInputTemplate*<br/>
'ndaki Kullanıcı girişinde her konumda görünebilen sabit karakterleri belirten bir maske şablonu dizesi. Karakter yer tutucusu olarak alt çizgi karakterini (' _ ') kullanın. *LpszInputTemplate* ve *lpszMask* parametre dizelerinin uzunluğu aynı olmalıdır.

*Chmaskınputtemplate*<br/>
'ndaki Çerçevenin Kullanıcı girişinde her bir geçersiz karakter için alternatifi için varsayılan bir karakter. Bu parametrenin varsayılan değeri alt çizgi (' _ ').

*lpszValid*<br/>
'ndaki Geçerli bir karakter kümesi içeren bir dize. NULL, tüm karakterlerin geçerli olduğunu gösterir. Bu parametrenin varsayılan değeri NULL.

### <a name="remarks"></a>Açıklamalar

Maskelenmiş düzenleme denetiminin maskesini oluşturmak için bu yöntemi kullanın. Sınıfından bir sınıf türetirsiniz `CMFCMaskedEdit` ve özel maske işleme için kendi kodunuzu kullanmak üzere [CMFCMaskedEdit:: IsMaskedChar](#ismaskedchar) metodunu geçersiz kılın.

Aşağıdaki tabloda varsayılan maske karakterleri listelenmektedir:

|Maske karakteri|Tanım|
|--------------------|----------------|
|D|Gurmukhi.|
|d|Sayı veya boşluk.|
|+|Artı (' + '), eksi ('-') veya boşluk.|
|C|Alfabetik karakter.|
|c|Alfabetik karakter veya boşluk.|
|A|Alfasayısal karakter.|
|a|Alfasayısal karakter veya boşluk.|
|*|Yazdırılabilir bir karakter.|

## <a name="cmfcmaskededitenableselectbygroup"></a><a name="enableselectbygroup"></a> CMFCMaskedEdit:: EnableSelectByGroup

Maskelenmiş düzenleme denetiminin, kullanıcının belirli gruplar girişi mi yoksa tüm girişleri mi seçmesini belirler.

```cpp
void EnableSelectByGroup(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Parametreler

*bEnable*<br/>
'ndaki Yalnızca grupları seçmek için TRUE; Metnin tamamını seçmek için FALSE. Varsayılan değer TRUE 'dur.

### <a name="remarks"></a>Açıklamalar

Maskelenmiş düzenleme denetiminin bir kullanıcının grup veya bütün metin ile seçmesine izin verip içermediğini belirtmek için bu işlevi kullanın.

Varsayılan olarak, grup seçimi etkindir. Bu durumda, Kullanıcı yalnızca sürekli geçerli karakter gruplarını seçebilir.

Örneğin, bir telefon numarasını doğrulamak için aşağıdaki maskelenmiş düzenleme denetimini kullanabilirsiniz:

```cpp
m_wndMaskEdit.EnableMask(
    _T(" ddd  ddd dddd"),  // Mask string
    _T("(___) ___-____"),  // Template string
    _T(' '));              // Default char

m_wndMaskEdit.SetValidChars(NULL); // All characters are valid.

m_wndMaskEdit.SetWindowText(_T("(425) 555-0187")); // Prompt
```

Gruba göre seçim etkinleştirilirse, Kullanıcı yalnızca "425", "555" veya "0187" dize gruplarını alabilir. Grup Seçimi devre dışıysa, Kullanıcı telefon numarasının tüm metnini alabilir: "(425) 555-0187".

## <a name="cmfcmaskededitenablesetmaskedcharsonly"></a><a name="enablesetmaskedcharsonly"></a> CMFCMaskedEdit::EnableSetMaskedCharsOnly

Metnin yalnızca maskelenmiş karakterlerle mi yoksa bütün maskeye karşı mi doğrulanacağını belirtir.

```cpp
void EnableSetMaskedCharsOnly(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Parametreler

*bEnable*<br/>
'ndaki Yalnızca maskeli karakterlerle Kullanıcı girişini doğrulamak için TRUE; Tüm maskeye karşı doğrulamak için FALSE. Varsayılan değer TRUE 'dur.

## <a name="cmfcmaskededitgetwindowtext"></a><a name="getwindowtext"></a> CMFCMaskedEdit:: GetWindowText

Maskelenmiş düzenleme denetiminden doğrulanan metni alır.

```
int GetWindowText(
    LPTSTR lpszStringBuf,
    int nMaxCount) const;

void GetWindowText(CString& rstrString) const;
```

### <a name="parameters"></a>Parametreler

*lpszStringBuf*<br/>
dışı Düzenleme denetiminden metni alan bir arabelleğin işaretçisi.

*nMaxCount*<br/>
'ndaki Alacak en fazla karakter sayısı.

*rstrString*<br/>
dışı Düzenleme denetiminden metni alan String nesnesine bir başvuru.

### <a name="return-value"></a>Dönüş Değeri

İlk yöntem aşırı yüklemesi, *lpszStringBuf* parametre arabelleğine kopyalanmış olan dizenin bayt sayısını döndürür; maskelenmiş düzenleme denetiminin metni yoksa 0.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, metin maskelenmiş düzenleme denetiminden *lpszStringBuf* buffer veya *rstrString* dizesine kopyalanır.

Bu yöntem [CWnd:: GetWindowText](../../mfc/reference/cwnd-class.md#getwindowtext)öğesini tekrar tanımlar.

## <a name="cmfcmaskededitismaskedchar"></a><a name="ismaskedchar"></a> CMFCMaskedEdit::IsMaskedChar

Belirtilen karakteri karşılık gelen maske karakteriyle doğrulamak için Framework tarafından çağırılır.

```
virtual BOOL IsMaskedChar(
    TCHAR chChar,
    TCHAR chMaskChar) const;
```

### <a name="parameters"></a>Parametreler

*chChar*<br/>
'ndaki Doğrulanacak karakter.

*chMaskChar*<br/>
'ndaki Maske dizesinden karşılık gelen karakter.

### <a name="return-value"></a>Dönüş Değeri

*ChChar* parametresi *chMaskChar* parametresi tarafından izin VERILEN karakter türü ise true. Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Giriş karakterlerini kendi kendinize doğrulamak için bu yöntemi geçersiz kılın. Maske karakterleri hakkında daha fazla bilgi için bkz. [CMFCMaskedEdit:: EnableMask](#enablemask) yöntemi.

## <a name="cmfcmaskededitsetvalidchars"></a><a name="setvalidchars"></a> CMFCMaskedEdit:: SetValidChars

Kullanıcının girebileceği geçerli karakterlerin bir dizesini belirtir.

```cpp
void SetValidChars(LPCTSTR lpszValid=NULL);
```

### <a name="parameters"></a>Parametreler

*lpszValid*<br/>
'ndaki Geçerli giriş karakterleri kümesini içeren bir dize. NULL, tüm karakterlerin geçerli olduğu anlamına gelir. Bu parametrenin varsayılan değeri NULL.

### <a name="remarks"></a>Açıklamalar

Geçerli karakterlerin bir listesini tanımlamak için bu yöntemi kullanın. Giriş karakteri bu listede değilse, maskelenmiş düzenleme denetimi bunu kabul etmez.

Aşağıdaki kod örneği yalnızca onaltılı sayıları kabul eder.

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

## <a name="cmfcmaskededitsetwindowtext"></a><a name="setwindowtext"></a> CMFCMaskedEdit:: SetWindowText

Maskelenmiş düzenleme denetiminde bir istem görüntüler.

```cpp
void SetWindowText(LPCTSTR lpszString);
```

### <a name="parameters"></a>Parametreler

*lpszString*<br/>
'ndaki İstem olarak kullanılacak, null ile sonlandırılmış bir dizeye işaret eder.

### <a name="remarks"></a>Açıklamalar

Bu yöntem denetim metnini ayarlar.

Bu yöntem [CWnd:: SetWindowText](../../mfc/reference/cwnd-class.md#setwindowtext)öğesini tekrar tanımlar.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[Cedıt sınıfı](../../mfc/reference/cedit-class.md)
