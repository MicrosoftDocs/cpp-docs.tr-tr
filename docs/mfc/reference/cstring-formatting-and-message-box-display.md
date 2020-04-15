---
title: CString Biçimlendirmesi ve İleti Kutusu Görüntüleme
ms.date: 11/04/2016
helpviewer_keywords:
- CString objects [MFC], formatting and message boxes
ms.assetid: d1068cf4-9cc5-4952-b9e7-d612c53cbc28
ms.openlocfilehash: d30d26ecf0e72ee33affe3df5b88c438ff83bb6b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366002"
---
# <a name="cstring-formatting-and-message-box-display"></a>CString Biçimlendirmesi ve İleti Kutusu Görüntüleme

Nesneleri biçimlendirmek ve ayrıştmak `CString` için bir dizi işlev sağlanır. `CString` Nesneleri işlemek gerektiğinde bu işlevleri kullanabilirsiniz, ancak bunlar özellikle ileti kutusu metninde görünecek dizeleri biçimlendirmek için yararlıdır.

Bu işlev ler grubu, ileti kutusunu görüntülemek için genel bir yordam da içerir.

### <a name="cstring-functions"></a>CString Fonksiyonları

|||
|-|-|
|[AfxExtractSubString](#afxextractsubstring)|Belirli bir kaynak dizesinden tek bir karakterle ayrılan alt dizeleri ayıklar.|
|[AfxFormatString1](#afxformatstring1)|Belirli bir dize, dize tablosunda bulunan bir dizedeki "%1" biçimi karakterleri yerine geçer.|
|[AfxFormatString2](#afxformatstring2)|Dize tablosunda bulunan bir dizedeki biçim karakterleri "%1" ve "%2" için iki dize yerine geçer.|
|[AfxMessageBox](#afxmessagebox)|İleti kutusunu görüntüler.|

### <a name="requirements"></a>Gereksinimler

  **Başlık** afxwin.h

## <a name="afxextractsubstring"></a><a name="afxextractsubstring"></a>AfxExtractSubString

Bu genel işlev, belirli bir kaynak dizesinden bir alt dize ayıklamak için kullanılabilir.

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
Çıkarılacak dizenin tam metnini içeren dize.

*iSubString*<br/>
*LpszFullString*ayıklamak için substring Sıfır tabanlı indeksi .

*chSep*<br/>
Alt dizeleri sınırlamak için kullanılan ayırıcı karakter.

### <a name="return-value"></a>Dönüş Değeri

Doğru eğer işlev sağlanan dizinde substring başarıyla ayıklanır; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bu işlev, bilinen tek bir karakter her alt dize yi ayırdığında kaynak dizeden birden çok alt dize ayıklamak için yararlıdır. Bu işlev, her çağrıldığında *lpszFullString* parametresinin başından itibaren arar.

*LpszFullString* NULL olarak ayarlanırsa veya fonksiyon belirtilen ayırıcı karakterin *iSubString*+1 oluşumlarını bulmadan *lpszFullString'in* sonuna ulaşırsa bu işlev FALSE döndürecektir. *lpszFullString* NULL olarak ayarlanmışsa *rString* parametresi orijinal değerinden değiştirilmez; aksi takdirde, belirtilen dizin için alt dize ayıklanamazsa, *rString* parametresi boş dize olarak ayarlanır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_Utilities#48](../../mfc/codesnippet/cpp/cstring-formatting-and-message-box-display_1.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Başlık** afxwin.h

## <a name="afxformatstring1"></a><a name="afxformatstring1"></a>AfxFormatString1

*NIDS*tarafından tanımlanan şablon dize kaynağındaki "%1" karakterlerinin herhangi bir örneği için *lpsz1* tarafından işaret edilen dize yerine geçer.

```
void  AfxFormatString1(
    CString& rString,
    UINT nIDS,
    LPCTSTR lpsz1);
```

### <a name="parameters"></a>Parametreler

*rString*<br/>
Değiştirme yapıldıktan `CString` sonra ortaya çıkan dizeyi içerecek bir nesneye başvuru.

*nIDS*<br/>
Değiştirmenin gerçekleştirileceği şablon dizesinin kaynak kimliği.

*lpsz1*<br/>
Şablon dizesinde biçim karakterleri "%1" yerini alacak bir dize.

### <a name="remarks"></a>Açıklamalar

Yeni oluşturulan dize *rString'te*depolanır. Örneğin, dize tablosundaki dize "Dosya %1 bulunamadı" ise ve *lpsz1* "C:\MYFILE"ya eşittir. TXT", sonra *rString* dize "Dosya C:\MYFILE içerecektir. TXT bulunamadı". Bu işlev, ileti kutularına ve diğer pencerelere gönderilen dizeleri biçimlendirmek için yararlıdır.

Biçim karakterleri "%1" dizede birden çok kez görünürse, birden çok değişiklik yapılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_Utilities#25](../../mfc/codesnippet/cpp/cstring-formatting-and-message-box-display_2.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Başlık** afxwin.h

## <a name="afxformatstring2"></a><a name="afxformatstring2"></a>AfxFormatString2

"%1" karakterlerinin herhangi bir örneği için *lpsz1* tarafından işaret edilen dize yerine geçer ve *lpsz2* tarafından işaret edilen dize,nIDS *nIDS*tarafından tanımlanan şablon dize kaynağında "%2".

```
void AfxFormatString2(
    CString& rString,
    UINT nIDS,
    LPCTSTR lpsz1,
    LPCTSTR lpsz2);
```

### <a name="parameters"></a>Parametreler

*rString*<br/>
Değiştirme yapıldıktan `CString` sonra ortaya çıkan dize içerecek olana yapılan başvuru.

*nIDS*<br/>
Değiştirmenin gerçekleştirileceği şablon dizesinin dize tablosu kimliği.

*lpsz1*<br/>
Şablon dizesinde biçim karakterleri "%1" yerini alacak bir dize.

*lpsz2*<br/>
Şablon dizesinde biçim karakterleri "%2" yerini alacak bir dize.

### <a name="remarks"></a>Açıklamalar

Yeni oluşturulan dize *rString'te*depolanır. Örneğin, dize tablosundaki dize "Dosya %1 dizinde %2 bulunamadı" ise, *lpsz1* "MYFILE'a işaret eder. TXT", ve *lpsz2* noktaları "C:\MYDIR", sonra *rString* dize içerecektir "Dosya MYFILE. TXT dizinde bulunamadı C:\MYDIR"

Biçim karakterleri "%1" veya "%2" dizesinde birden çok kez görünürse, birden çok değişiklik yapılır. Sayısal sırada olmak zorunda değiller.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_Utilities#26](../../mfc/codesnippet/cpp/cstring-formatting-and-message-box-display_3.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Başlık** afxwin.h

## <a name="afxmessagebox"></a><a name="afxmessagebox"></a>AfxMessageBox

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

*lpszMetin*<br/>
İleti kutusunda `CString` görüntülenecek iletiyi içeren bir nesneye veya null-sonlandırılan dizeye işaret eder.

*nTipi*<br/>
İleti kutusunun stili. İleti kutusu [stillerinden](../../mfc/reference/styles-used-by-mfc.md#message-box-styles) herhangi birini kutuya uygulayın.

*nIDYardım*<br/>
İleti için Yardım bağlam kimliği; 0, uygulamanın varsayılan Yardım bağlamında kullanılacağını gösterir.

*nIDPrompt*<br/>
Dize tablosundaki bir dizeye başvurmak için kullanılan benzersiz bir kimlik.

### <a name="return-value"></a>Dönüş Değeri

İleti kutusunu görüntülemek için yeterli bellek yoksa sıfır; aksi takdirde, aşağıdaki değerlerden biri döndürülür:

- IDABORT İptal düğmesi seçildi.

- IDCANCEL İptal düğmesi seçildi.

- IDIGNORE Yoksay düğmesi seçildi.

- IDNO Hayır düğmesi seçildi.

- İDOK Tamam düğmesi seçildi.

- IDRETRY Yeniden Deneme düğmesi seçildi.

- IDYES Evet düğmesi seçildi.

İleti kutusunda İptal düğmesi varsa, ESC tuşuna basıldığında veya İptal düğmesine basıldığında IDCANCEL değeri döndürülür. İleti kutusunun İptal düğmesi yoksa, ESC tuşuna basmanın bir etkisi yoktur.

[AfxFormatString1](#afxformatstring1) ve [AfxFormatString2](#afxformatstring2) işlevleri, ileti kutusunda görünen metni biçimlendirmede yararlı olabilir.

### <a name="remarks"></a>Açıklamalar

Bu aşırı yüklü işlevin ilk biçimi, ileti kutusunda *lpszText* tarafından işaret edilen bir metin dizesini görüntüler ve Yardım bağlamını tanımlamak için *nIDHelp'i* kullanır. Yardım bağlamı, kullanıcı Yardım anahtarına (genellikle F1) bastığında ilişkili bir Yardım konusuna atlamak için kullanılır.

İşlevin ikinci biçimi, ileti kutusunda bir ileti görüntülemek için Kimlik *nIDPrompt* ile string kaynağını kullanır. İlişkili Yardım sayfası *nIDHelp*değeri ile bulunur. *nIDHelp* varsayılan değeri (-1) kullanılırsa, string kaynak kimliği, *nIDPrompt*, Yardım bağlamı için kullanılır. Yardım bağlamlarını tanımlama hakkında daha fazla bilgi için [Teknik Not 28'e](../../mfc/tn028-context-sensitive-help-support.md)bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCWindowing#133](../../mfc/reference/codesnippet/cpp/cstring-formatting-and-message-box-display_4.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve Küreseller](../../mfc/reference/mfc-macros-and-globals.md)<br/>
[CStringT Sınıfı](../../atl-mfc-shared/reference/cstringt-class.md)
