---
description: 'Daha fazla bilgi edinin: CString Formatting and Message-Box Display'
title: CString Biçimlendirmesi ve İleti Kutusu Görüntüleme
ms.date: 11/04/2016
helpviewer_keywords:
- CString objects [MFC], formatting and message boxes
ms.assetid: d1068cf4-9cc5-4952-b9e7-d612c53cbc28
ms.openlocfilehash: a3c91a2a8a6f80235a834811433467797d5a37a7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97264524"
---
# <a name="cstring-formatting-and-message-box-display"></a>CString Biçimlendirmesi ve İleti Kutusu Görüntüleme

Nesneleri biçimlendirmek ve ayrıştırmak için bir dizi işlev sağlanır `CString` . Nesneleri her işlemek gerektiğinde bu işlevleri kullanabilirsiniz `CString` , ancak bunlar özellikle ileti kutusu metninde görünecek dizeleri biçimlendirmek için yararlıdır.

Bu işlev grubu ayrıca bir ileti kutusu görüntülemek için genel bir yordam içerir.

### <a name="cstring-functions"></a>CString Işlevleri

|Ad|Açıklama|
|-|-|
|[AfxExtractSubString](#afxextractsubstring)|Belirli bir kaynak dizeden tek bir karakterle ayrılmış alt dizeleri ayıklar.|
|[AfxFormatString1](#afxformatstring1)|"%1" biçim karakterleri için dize tablosunda yer alan bir dizedeki belirli bir dizeyi değiştirir.|
|[AfxFormatString2](#afxformatstring2)|"%1" ve "%2" biçim karakterleri için dize tablosunda yer alan bir dizedeki iki dizeyi değiştirir.|
|[AfxMessageBox](#afxmessagebox)|Bir ileti kutusu görüntüler.|

### <a name="requirements"></a>Gereksinimler

  **Başlık** Afxwin. h

## <a name="afxextractsubstring"></a><a name="afxextractsubstring"></a> AfxExtractSubString

Bu genel işlev, belirli bir kaynak dizeden bir alt dize ayıklamak için kullanılabilir.

```
BOOL AFXAPI AfxExtractSubString (
    CString& rString,
    LPCTSTR lpszFullString,
    int iSubString,
    TCHAR chSep  = '\n');
```

### <a name="parameters"></a>Parametreler

*rString*<br/>
Tek bir alt dize alacak bir [CString](../../atl-mfc-shared/using-cstring.md) nesnesine başvuru.

*lpszFullString*<br/>
Dizeden Ayıklanacak dizenin tam metnini içeren dize.

*ıubstring*<br/>
*LpszFullString* öğesinden Ayıklanacak alt dizenin sıfır tabanlı dizini.

*chSep*<br/>
Alt dizeleri sınırlandırmak için kullanılan ayırıcı karakter.

### <a name="return-value"></a>Dönüş Değeri

İşlev, alt dizeyi belirtilen dizinde başarıyla ayıkladığında TRUE. Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Bu işlev, bilinen bir tek karakter her alt dizeyi ayırdığı zaman bir kaynak dizeden birden çok alt dizeyi ayıklamak için faydalıdır. Bu işlev, her çağrılışında *lpszFullString* parametresinin başından itibaren arar.

Bu işlev, *LPSZFULLSTRING* null olarak ayarlandıysa ya da işlev, belirtilen ayırıcı karakterin *ısubstring*+ 1 tekrarlamalarını bulmaksızın *lpszFullString* sonuna ulaşırsa false döndürür. *LPSZFULLSTRING* null olarak ayarlandıysa, *rString* parametresi özgün değerinden değiştirilmez; Aksi halde, belirtilen dizin için alt dize ayıklanamadı *rString* parametresi boş dizeye ayarlanır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_Utilities#48](../../mfc/codesnippet/cpp/cstring-formatting-and-message-box-display_1.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Başlık** Afxwin. h

## <a name="afxformatstring1"></a><a name="afxformatstring1"></a> AfxFormatString1

"%1" karakterlerinin herhangi bir örneği için *lpsz1* tarafından işaret edilen dizeyi, *NIDS* tarafından tanımlanan şablon dizesi kaynağında değiştirir.

```cpp
void  AfxFormatString1(
    CString& rString,
    UINT nIDS,
    LPCTSTR lpsz1);
```

### <a name="parameters"></a>Parametreler

*rString*<br/>
`CString`Değiştirme gerçekleştirildikten sonra sonuçtaki dizeyi içeren bir nesneye başvuru.

*Nkimlikler*<br/>
Değiştirme gerçekleştirileceği şablon dizesinin kaynak KIMLIĞI.

*lpsz1*<br/>
Şablon dizesindeki "%1" biçim karakterlerinin yerini alacak bir dize.

### <a name="remarks"></a>Açıklamalar

Yeni oluşturulan dize, *rString* içinde depolanır. Örneğin, dize tablosundaki dize "dosya %1 bulunamadı" ise ve *lpsz1* "C:\MYFILE.TXT" değerine eşitse, *rstring* "dosya C:\MYFILE.TXT bulunamadı" dizesini içerir. Bu işlev ileti kutularına ve diğer pencereler için gönderilen dizeleri biçimlendirmek için yararlıdır.

"%1" biçim karakterleri dizede birden çok kez görünürse, birden çok değiştirme yapılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_Utilities#25](../../mfc/codesnippet/cpp/cstring-formatting-and-message-box-display_2.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Başlık** Afxwin. h

## <a name="afxformatstring2"></a><a name="afxformatstring2"></a> AfxFormatString2

"%1" karakterlerinin herhangi bir örneği için *lpsz1* tarafından işaret edilen dizeyi ve *NIDS* tarafından tanımlanan şablon dizesi kaynağındaki "%2" karakterlerinin herhangi bir örneği için *lpsz2* tarafından işaret edilen dizeyi değiştirir.

```cpp
void AfxFormatString2(
    CString& rString,
    UINT nIDS,
    LPCTSTR lpsz1,
    LPCTSTR lpsz2);
```

### <a name="parameters"></a>Parametreler

*rString*<br/>
`CString`Değiştirme gerçekleştirildikten sonra sonuç dizesini içerecek olan öğesine başvuru.

*Nkimlikler*<br/>
Değiştirme gerçekleştirileceği şablon dizesinin dize tablo KIMLIĞI.

*lpsz1*<br/>
Şablon dizesindeki "%1" biçim karakterlerinin yerini alacak bir dize.

*lpsz2*<br/>
Şablon dizesindeki "%2" biçim karakterlerinin yerini alacak bir dize.

### <a name="remarks"></a>Açıklamalar

Yeni oluşturulan dize, *rString* içinde depolanır. Örneğin, dize tablosundaki dize "%2 dizininde bulunamayan dosya %1", *lpsz1* "MYFILE.TXT" ve *lpsz2* "c:\mydir" olarak Işaret ediyorsa, *rString* "MYFILE.TXT dosya c:\dir dizininde bulunamadı" dizesini içerir.

"%1" veya "%2" biçim karakterleri dizede birden çok kez görünürse, birden çok değişim yapılır. Bunların sayısal sırada olması gerekmez.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_Utilities#26](../../mfc/codesnippet/cpp/cstring-formatting-and-message-box-display_3.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Başlık** Afxwin. h

## <a name="afxmessagebox"></a><a name="afxmessagebox"></a> AfxMessageBox

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
`CString`İleti kutusunda görüntülenecek iletiyi içeren bir nesneye veya null ile sonlandırılmış dizeye işaret eder.

*nTür*<br/>
İleti kutusunun stili. Kutuya [ileti kutusu stillerinden](../../mfc/reference/styles-used-by-mfc.md#message-box-styles) birini uygulayın.

*nIDHelp*<br/>
İleti için yardım bağlam KIMLIĞI; 0, uygulamanın varsayılan yardım bağlamını kullanacağını gösterir.

*nIDPrompt*<br/>
Dize tablosundaki bir dizeye başvurmak için kullanılan benzersiz bir KIMLIK.

### <a name="return-value"></a>Dönüş Değeri

İleti kutusunu göstermek için yeterli bellek yoksa sıfır; Aksi takdirde, aşağıdaki değerlerden biri döndürülür:

- Durdur düğmesi seçildi.

- IDCANCEL Iptal düğmesi seçildi.

- IDıGNORE yoksay düğmesi seçildi.

- IDNO düğmesi seçilmedi.

- IDOK Tamam düğmesi seçildi.

- IDRETRY yeniden dene düğmesi seçildi.

- IDYES Evet düğmesi seçilmiştir.

İleti kutusunda bir Iptal düğmesi varsa, ESC tuşuna basıldığında ya da Iptal düğmesi seçiliyse ıDCANCEL değeri döndürülür. İleti kutusunda Iptal düğmesi yoksa, ESC tuşuna basıldığında hiçbir etkisi olmaz.

[AfxFormatString1](#afxformatstring1) ve [AfxFormatString2](#afxformatstring2) işlevleri, bir ileti kutusunda görüntülenen metinde biçimlendirme yararlı olabilir.

### <a name="remarks"></a>Açıklamalar

Bu aşırı yüklenmiş işlevin ilk formu ileti kutusunda *lpszText* tarafından işaret edilen bir metin dizesini görüntüler ve bir yardım bağlamını anlatmak Için *nIDHelp* kullanır. Yardım bağlamı, Kullanıcı Yardım tuşuna bastığında (genellikle F1) ilişkili bir yardım konusuna geçmek için kullanılır.

İşlevin ikinci formu, ileti kutusunda bir ileti göstermek için ID *nIDPrompt* ile dize kaynağını kullanır. İlişkili Yardım sayfası, *nIDHelp* değeri aracılığıyla bulunur. Varsayılan *nIDHelp* değeri kullanılırsa (-1), DIZE kaynak kimliği, *nIDPrompt*, yardım bağlamı için kullanılır. Yardım bağlamlarını tanımlama hakkında daha fazla bilgi için bkz. [teknik notta 28](../../mfc/tn028-context-sensitive-help-support.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#133](../../mfc/reference/codesnippet/cpp/cstring-formatting-and-message-box-display_4.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve genel öğeler](../../mfc/reference/mfc-macros-and-globals.md)<br/>
[CStringT sınıfı](../../atl-mfc-shared/reference/cstringt-class.md)
