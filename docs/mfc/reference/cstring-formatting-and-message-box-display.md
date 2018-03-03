---
title: "CString biçimlendirmesi ve ileti kutusu görüntüleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros.strings
dev_langs:
- C++
helpviewer_keywords:
- CString objects [MFC], formatting and message boxes
ms.assetid: d1068cf4-9cc5-4952-b9e7-d612c53cbc28
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7bc86e066e57978bee0953e233edbb2aefbe61c5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cstring-formatting-and-message-box-display"></a>CString Biçimlendirmesi ve İleti Kutusu Görüntüleme
Biçimlendirmek ve ayrıştırmak için bir dizi işlev sağlanan `CString` nesneleri. İşlemek sahip olduğunda bu işlevler kullanabilirsiniz `CString` nesneleri, ancak ileti kutusu metin olarak görünür dizeleri biçimlendirme için yararlıdır.  
  
 Bu grubun işlevleri de bir ileti kutusu görüntüleme için genel bir yordamı içerir.  
  
### <a name="cstring-functions"></a>CString işlevleri  
  
|||  
|-|-|  
|[AfxExtractSubString](#afxextractsubstring)|Alt dizeler tek bir karakter tarafından belirtilen kaynak dizeden ayrılmış ayıklar.|  
|[AfxFormatString1](#afxformatstring1)|Alternatifler dize tabloda bir dize biçimi karakterleri "%1" için belirtilen bir dize içeriyor.|  
|[AfxFormatString2](#afxformatstring2)|Alternatifler iki dize biçimi için "%1" ve "% dizesi tabloda bulunan 2" bir dizedeki karakter.|  
|[AfxMessageBox](#afxmessagebox)|Bir ileti kutusu görüntüler.|  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxwin.h  
  
##  <a name="afxextractsubstring"></a>AfxExtractSubString  
 Bu genel işlevi, bir alt dizenin belirtilen kaynak çıkartmak için kullanılabilir.  
  
```   
BOOL AFXAPI AfxExtractSubString (
    CString& rString,  
    LPCTSTR lpszFullString,  
    int iSubString,  
    TCHAR chSep  = '\n'); 
```  
  
### <a name="parameters"></a>Parametreler  
 *rString*  
 -   Başvuru bir [CString](../../atl-mfc-shared/using-cstring.md) tek tek bir alt dizenin alacak nesnesi.  
  
 *lpszFullString*  
 -   Tam metin dizesinin ayıklamak için içeren dize.  
  
 *iSubString*  
 -   Sıfır tabanlı dizini ayıklamak için alt dizeyi *lpszFullString*.  
  
 *chSep*  
 -   Alt dizeler sınırlandırmak için kullanılan bir ayırıcı karakter.  
  
### <a name="return-value"></a>Dönüş Değeri  
 **DOĞRU** işlevi başarıyla sağlanan dizinindeki; alt dizenin ayıklanacağı, aksi takdirde, **FALSE**.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev, bilinen tek bir karakter her substring ayıran bir kaynak dizeden birden çok alt dizeler ayıklanmasına yararlıdır. Bu işlev arar başından itibaren `lpszFullString` parametresi çağırıldığında her zaman.  
  
 Bu işlev yanlış ya da olursa döndürür `lpszFullString` ayarlanır **NULL** veya işlev sonuna ulaştığında `lpszFullString` bulma olmadan `iSubString`belirtilen ayırıcı karakter + 1 oluşumu. `rString` Parametresi değiştirilmeyecek özgün değeri varsa `lpszFullString` ayarlandı **NULL**; Aksi halde, `rString` parametresi, boş dize olarak ayarlanırsa, alt dizeyi değil ayıklanan, için belirtilen dizini.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_Utilities#48](../../mfc/codesnippet/cpp/cstring-formatting-and-message-box-display_1.cpp)]  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxwin.h  
  
##  <a name="afxformatstring1"></a>AfxFormatString1  
 Gösterdiği dize değiştirir `lpsz1` tarafından tanımlanan şablon dize kaynağı "%1" karakter tüm örnekleri için `nIDS`.  
  
```  
void  AfxFormatString1(
    CString& rString,  
    UINT nIDS,  
    LPCTSTR lpsz1); 
```  
  
### <a name="parameters"></a>Parametreler  
 `rString`  
 Bir başvuru bir `CString` değiştirme işlemi yapıldıktan sonra sonuç dizeyi içeren nesne.  
  
 `nIDS`  
 Değiştirme gerçekleştirilecek şablonu dizesi kaynak kimliği.  
  
 `lpsz1`  
 Biçim değiştirecek bir dize "%1" şablonu dizesi karakter.  
  
### <a name="remarks"></a>Açıklamalar  
 Yeni oluşturulmamış dize depolanan `rString`. Örneğin, dize tablosu dizesindeki "Dosyası %1 bulunamadı" ise ve `lpsz1` "C:\MYFILE. eşittir TXT", ardından `rString` karakter dizesi"dosyası C:\MYFILE. TXT"bulunamadı. Bu işlev, ileti kutuları ve diğer windows gönderilen dizeleri biçimlendirme için yararlıdır.  
  
 "%1" biçimi karakterler dizesini birden çok kez görünüyorsa, birden çok değişimler yapılacaktır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_Utilities#25](../../mfc/codesnippet/cpp/cstring-formatting-and-message-box-display_2.cpp)]  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxwin.h  
  
##  <a name="afxformatstring2"></a>AfxFormatString2  
 Gösterdiği dize değiştirir `lpsz1` "%1" karakterleri ve gösterdiği dize tüm örnekleri için `lpsz2` tarafından tanımlanan şablon dize kaynağı "%2" karakter tüm örnekleri için `nIDS`.  
  
```   
void AfxFormatString2(
    CString& rString,  
    UINT nIDS,  
    LPCTSTR lpsz1,  
    LPCTSTR lpsz2); 
```  
  
### <a name="parameters"></a>Parametreler  
 `rString`  
 Bir başvuru `CString` değiştirme işlemi yapıldıktan sonra sonuç dize içerecek.  
  
 `nIDS`  
 Değiştirme gerçekleştirilecek şablonu dizesi dize tablo kimliği.  
  
 `lpsz1`  
 Biçim değiştirecek bir dize "%1" şablonu dizesi karakter.  
  
 `lpsz2`  
 Biçim değiştirecek bir dize şablonu dizesi "%2" karakter.  
  
### <a name="remarks"></a>Açıklamalar  
 Yeni oluşturulmamış dize depolanan `rString`. Örneğin, dize tablosu dizesindeki "Dosyası %1 %2 dizini bulunamadı" ise `lpsz1` işaret "MYFILE. TXT", ve `lpsz2` "C:\MYDIR", ardından işaret `rString` karakter dizesi"dosyası MYFILE. TXT"C:\MYDIR dizinde bulunamadı  
  
 "%1" biçimi karakter veya "%2" dizesi içinde birden çok kez görüntülenir, birden çok değişimler yapılacaktır. Sayısal olması gerekmez.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_Utilities#26](../../mfc/codesnippet/cpp/cstring-formatting-and-message-box-display_3.cpp)]  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxwin.h  
  
##  <a name="afxmessagebox"></a>AfxMessageBox  
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
 `lpszText`  
 İşaret eden bir `CString` nesne veya ileti kutusunda görüntülenecek iletiyi içeren null ile sonlandırılmış dize.  
  
 `nType`  
 İleti kutusu stili. Herhangi biri geçerli [ileti kutusu stilleri](../../mfc/reference/styles-used-by-mfc.md#message-box-styles) kutusuna.  
  
 `nIDHelp`  
 Yardım içerik kimliği iletisi için; uygulamanın varsayılan Yardım içeriği kullanılacak 0 gösterir.  
  
 `nIDPrompt`  
 Dize tablosu içindeki bir dizeye başvurmak için kullanılan benzersiz bir kimlik.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İleti kutusu görüntülemek için yeterli bellek varsa sıfır; Aksi takdirde, aşağıdaki değerlerden birini döndürülür:  
  
- **IDABORT** iptal düğmesi seçilmedi.  
  
- **IDCANCEL** iptal düğmesi seçilmedi.  
  
- **IDIGNORE** Yoksay düğmesini seçilmedi.  
  
- **IDNO** Hayır düğmesi seçilmedi.  
  
- **IDOK** Tamam düğmesi seçilmedi.  
  
- **IDRETRY** yeniden dene düğmesi seçilmedi.  
  
- **IDYES** Evet düğmesi seçilmedi.  
  
 Bir ileti kutusu iptal düğmesi varsa **IDCANCEL** değeri döndürülecek ESC tuşuna basılana ya da iptal düğmesi seçilir. İleti kutusunda İptal düğmesi varsa, ESC tuşuna basarak etkisizdir.  
  
 İşlevler [AfxFormatString1](#afxformatstring1) ve [AfxFormatString2](#afxformatstring2) bir ileti kutusunda görüntülenen metni biçimlendirmede yararlı olabilir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu ilk form tarafından için bir metin dizesi işaret işlevi görüntüler aşırı `lpszText` kullanır ve ileti kutusu `nIDHelp` Yardım bağlamı açıklamak için. Yardım içeriği, kullanıcı (genellikle F1) Yardım tuşuna bastığında ilişkili bir Yardım konusu atlamak için kullanılır.  
  
 İşlevin ikinci form dize kaynak kimliği ile kullanır `nIDPrompt` ileti kutusu içinde bir ileti görüntülemek için. İlişkili Yardım sayfası değeri bulunan `nIDHelp`. Varsa varsayılan değer olan `nIDHelp` kullanılan (-1), olan dize kaynak kimliği `nIDPrompt`, Yardım bağlamı için kullanılır. Yardım içerikleri tanımlama hakkında daha fazla bilgi için bkz: [Teknik Not 28](../../mfc/tn028-context-sensitive-help-support.md).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCWindowing#133](../../mfc/reference/codesnippet/cpp/cstring-formatting-and-message-box-display_4.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md)   
 [CStringT Sınıfı](../../atl-mfc-shared/reference/cstringt-class.md)
