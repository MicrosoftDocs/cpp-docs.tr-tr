---
title: CString biçimlendirmesi ve ileti kutusu görüntüleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros.strings
dev_langs:
- C++
helpviewer_keywords:
- CString objects [MFC], formatting and message boxes
ms.assetid: d1068cf4-9cc5-4952-b9e7-d612c53cbc28
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 125d0d3ec1549b9eba46cbfebfb7ecfe2c2186d9
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46387191"
---
# <a name="cstring-formatting-and-message-box-display"></a>CString Biçimlendirmesi ve İleti Kutusu Görüntüleme

Biçimlendirme ve ayrıştırma için çok sayıda işlev sağlanan `CString` nesneleri. İşlemek olduğunda, bu işlevler kullanabilirsiniz `CString` nesneleri, ancak ileti kutusu metinde görünür dizeleri biçimlendirme için yararlıdır.

Bu grubun işlevleri, ayrıca bir ileti kutusu görüntülemek için genel bir yordamı içerir.

### <a name="cstring-functions"></a>CString işlevleri

|||
|-|-|
|[AfxExtractSubString](#afxextractsubstring)|Belirtilen kaynak dizeden tek bir karakter ile ayrılmış alt dizeler ayıklar.|
|[AfxFormatString1](#afxformatstring1)|Alternatifler dize tablosunda bir dizedeki karakterleri "%1" biçimlendirmek için belirli bir dize içeriyordu.|
|[AfxFormatString2](#afxformatstring2)|Alternatifler iki dize biçimi için "%1" ve "% dize tablosunda bulunan 2" bir dizedeki karakter.|
|[AfxMessageBox](#afxmessagebox)|Bir ileti kutusu görüntüler.|

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxwin.h

##  <a name="afxextractsubstring"></a>  AfxExtractSubString

Bu genel işlevi, bir alt dizenin belirtilen kaynak çıkartmak için kullanılabilir.

```
BOOL AFXAPI AfxExtractSubString (
    CString& rString,
    LPCTSTR lpszFullString,
    int iSubString,
    TCHAR chSep  = '\n');
```

### <a name="parameters"></a>Parametreler

*rString*<br/>
Başvuru bir [CString](../../atl-mfc-shared/using-cstring.md) nesnesini tek bir alt dize alır.

*lpszFullString*<br/>
Tam metin ayıklamak için dize içeren dize.

*iSubString*<br/>
Sıfır tabanlı dizin ayıklamak için alt dizenin *lpszFullString*.

*chSep*<br/>
Alt dizeler sınırlandırmak için kullanılan ayırıcı karakter.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarıyla alt dizenin belirtilen dizindeki ayıklanan TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Bu işlev, her alt dizenin bilinen tek bir karakter ayıran bir kaynak dizedeki birden çok alt dizeler ayıklanmasında yararlıdır. Bu işlev arar başından *lpszFullString* parametresi çağırıldığında her zaman.

Bu işlev ya da FALSE döndüreceği *lpszFullString* NULL olarak ayarlandı veya işlevin sonuna ulaşıldığında *lpszFullString* bulma olmadan *iSubString*+ 1 Belirtilen ayırıcıyı tekrarı. *RString* parametresi değiştirilmeyecek özgün değeri varsa *lpszFullString* NULL; Aksi takdirde ayarlandı *rString* parametresi varsa boş dize olarak ayarlayın alt dizenin belirtilen dizin için ayıklanamadı.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_Utilities#48](../../mfc/codesnippet/cpp/cstring-formatting-and-message-box-display_1.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxwin.h

##  <a name="afxformatstring1"></a>  AfxFormatString1

İşaret ettiği dizeyi değiştirir *lpsz1* tarafından tanımlanan şablon dize kaynağı "%1" karakterleri, tüm örnekler için *nIDS*.

```
void  AfxFormatString1(
    CString& rString,
    UINT nIDS,
    LPCTSTR lpsz1);
```

### <a name="parameters"></a>Parametreler

*rString*<br/>
Bir başvuru bir `CString` değiştirme işlemi gerçekleştirildikten sonra sonuç dizesi içeren bir nesne.

*nIDS*<br/>
Değiştirme gerçekleştirilecek şablon dize kaynak kimliği.

*lpsz1*<br/>
"%1" şablonu dizesi karakterlerin biçimi yerini alacak bir dize.

### <a name="remarks"></a>Açıklamalar

Yeni bir biçimlendirilmiş dize depolanan *rString*. Örneğin, dize tablosunda bir dize "Dosyası %1 bulunamadı" ise ve *lpsz1* "için C:\MYFILE. eşittir TXT", ardından *rString* "dosyası C:\MYFILE. dize içerir TXT"bulunamadı. Bu işlev, ileti kutularını ve diğer windows gönderilen dizeleri biçimlendirme için yararlıdır.

Biçim karakterleri "%1" dizesinde birden çok kez görünüyorsa, birden çok değişimler sunulacaktır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_Utilities#25](../../mfc/codesnippet/cpp/cstring-formatting-and-message-box-display_2.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxwin.h

##  <a name="afxformatstring2"></a>  AfxFormatString2

İşaret ettiği dizeyi değiştirir *lpsz1* tüm karakterleri "%1" örneklerini ve işaret ettiği dizeyi *lpsz2* şablon dize kaynağı "%2" karakterleri, tüm örnekler için tarafından tanımlanan *nIDS*.

```
void AfxFormatString2(
    CString& rString,
    UINT nIDS,
    LPCTSTR lpsz1,
    LPCTSTR lpsz2);
```

### <a name="parameters"></a>Parametreler

*rString*<br/>
Bir başvuru `CString` değiştirme işlemi gerçekleştirildikten sonra sonuç dize içerecek.

*nIDS*<br/>
Değiştirme gerçekleştirilecek şablonu dizesi dize tablo kimliği.

*lpsz1*<br/>
"%1" şablonu dizesi karakterlerin biçimi yerini alacak bir dize.

*lpsz2*<br/>
"%2" şablonu dizesi karakterlerin biçimi yerini alacak bir dize.

### <a name="remarks"></a>Açıklamalar

Yeni bir biçimlendirilmiş dize depolanan *rString*. Örneğin, "Dosyası %1 %2 dizini içinde bulunamadı" dize tablosunda bir dize ise, *lpsz1* işaret "MYFILE için. "TXT", ve *lpsz2* "C:\MYDIR", ardından işaret *rString* "MYFILE dosyası. dize içerir TXT"C:\MYDIR dizinde bulunamadı

Biçim karakterleri "%1" veya "%2" dizesinde birden çok kez görünmesi, birden çok değişimler sunulacaktır. Sayısal olması gerekmez.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_Utilities#26](../../mfc/codesnippet/cpp/cstring-formatting-and-message-box-display_3.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxwin.h

##  <a name="afxmessagebox"></a>  AfxMessageBox

Ekranda bir ileti kutusu görüntüler.

```
int AfxMessageBox(
    LPCTSTR lpszText,
    UINT nType = MB_OK,
    UINT nIDHelp = 0);

int AFXAPI AfxMessageBox(
    UINT nIDPrompt,
    UINT nType = MB_OK,
    UINT nIDHelp = (UINT) -1);
```

### <a name="parameters"></a>Parametreler

*lpszText*<br/>
İşaret eden bir `CString` nesne veya ileti kutusunda görüntülenecek iletiyi içeren null ile sonlandırılmış dize.

*nTür*<br/>
İleti kutusunun stili. Atanamadığı [ileti kutusu stilleri](../../mfc/reference/styles-used-by-mfc.md#message-box-styles) kutusu.

*nIDHelp*<br/>
İleti için Yardım içeriği kimliği; 0 uygulamanın varsayılan Yardım içeriğinin kullanılacak gösterir.

*nIDPrompt*<br/>
Dize tablosunda bir dize başvurmak için kullanılan benzersiz kimliği.

### <a name="return-value"></a>Dönüş Değeri

İleti kutusu görüntülemek için yeterli bellek yoksa sıfır; Aksi halde aşağıdaki değerlerden biri döndürülür:

- IDABORT Durdur düğmesi seçilmiştir.

- IDCANCEL iptal düğmesi seçilmiştir.

- IDIGNORE yoksay düğmesi seçilmiştir.

- IDNO Hayır düğmesi seçilmiştir.

- IDOK Tamam düğmesi seçilmiştir.

- IDRETRY yeniden dene düğmesi seçilmiştir.

- IDYES Evet düğmesi seçilmiştir.

Bir ileti kutusunda İptal düğmesi varsa, ESC tuşuna basıldığında veya iptal düğmesi seçili IDCANCEL değeri döndürülür. İleti kutusunda İptal düğmesi varsa, ESC tuşuna basarak etkisizdir.

İşlevleri [AfxFormatString1](#afxformatstring1) ve [AfxFormatString2](#afxformatstring2) bir ileti kutusunda görünen metni biçimlendirirken olabilir.

### <a name="remarks"></a>Açıklamalar

Bu ilk formu aşırı yüklenmiş bir metin dizesi tarafından işaret edilen işlevi görüntüler *lpszText* kullanır ve ileti kutusu içinde *nIDHelp* Yardım içeriğini açıklamak için. Kullanıcı Yardım tuşuna (genellikle F1) bastığında, ilişkili bir Yardım konusuna atlamak için Yardım bağlamında kullanılır.

İşlevin ikinci formu Kimliğiyle dize kaynağını kullanır *nIDPrompt* ileti kutusunda bir ileti görüntülemek için. İlişkili Yardım sayfası değeri aracılığıyla bulunur *nIDHelp*. Varsa varsayılan değer olan *nIDHelp* kullanılan (-1), dize kaynak kimliği *nIDPrompt*, Yardım bağlamında kullanılır. Yardım bağlamlarının tanımlanması hakkında daha fazla bilgi için bkz. [Teknik Not 28](../../mfc/tn028-context-sensitive-help-support.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#133](../../mfc/reference/codesnippet/cpp/cstring-formatting-and-message-box-display_4.cpp)]

## <a name="see-also"></a>Ayrıca Bkz.

[Makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md)<br/>
[CStringT Sınıfı](../../atl-mfc-shared/reference/cstringt-class.md)
