---
title: CFindReplaceDialog sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CFindReplaceDialog
- AFXDLGS/CFindReplaceDialog
- AFXDLGS/CFindReplaceDialog::CFindReplaceDialog
- AFXDLGS/CFindReplaceDialog::Create
- AFXDLGS/CFindReplaceDialog::FindNext
- AFXDLGS/CFindReplaceDialog::GetFindString
- AFXDLGS/CFindReplaceDialog::GetNotifier
- AFXDLGS/CFindReplaceDialog::GetReplaceString
- AFXDLGS/CFindReplaceDialog::IsTerminating
- AFXDLGS/CFindReplaceDialog::MatchCase
- AFXDLGS/CFindReplaceDialog::MatchWholeWord
- AFXDLGS/CFindReplaceDialog::ReplaceAll
- AFXDLGS/CFindReplaceDialog::ReplaceCurrent
- AFXDLGS/CFindReplaceDialog::SearchDown
- AFXDLGS/CFindReplaceDialog::m_fr
dev_langs:
- C++
helpviewer_keywords:
- CFindReplaceDialog [MFC], CFindReplaceDialog
- CFindReplaceDialog [MFC], Create
- CFindReplaceDialog [MFC], FindNext
- CFindReplaceDialog [MFC], GetFindString
- CFindReplaceDialog [MFC], GetNotifier
- CFindReplaceDialog [MFC], GetReplaceString
- CFindReplaceDialog [MFC], IsTerminating
- CFindReplaceDialog [MFC], MatchCase
- CFindReplaceDialog [MFC], MatchWholeWord
- CFindReplaceDialog [MFC], ReplaceAll
- CFindReplaceDialog [MFC], ReplaceCurrent
- CFindReplaceDialog [MFC], SearchDown
- CFindReplaceDialog [MFC], m_fr
ms.assetid: 610f0b5d-b398-4ef6-8c05-e9d6641e50a8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 635019011b655f338e499724c788bc433df5d571
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36957084"
---
# <a name="cfindreplacedialog-class"></a>CFindReplaceDialog sınıfı
Standart dize Bul ve Değiştir iletişim kutuları, uygulamanızda uygulamak sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CFindReplaceDialog : public CCommonDialog  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CFindReplaceDialog::CFindReplaceDialog](#cfindreplacedialog)|Oluşturmak için bu işlevi çağırmak bir `CFindReplaceDialog` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CFindReplaceDialog::Create](#create)|Oluşturur ve görüntüler bir `CFindReplaceDialog` iletişim kutusu.|  
|[CFindReplaceDialog::FindNext](#findnext)|Kullanıcının Sonrakini Bul dizesinin bulmak istediği olup olmadığını belirlemek için bu işlevini çağırın.|  
|[CFindReplaceDialog::GetFindString](#getfindstring)|Geçerli Bul dizesini almak için bu işlevini çağırın.|  
|[CFindReplaceDialog::GetNotifier](#getnotifier)|Almak için bu işlevi çağırmak **FINDREPLACE** kayıtlı ileti işleyicinizi yapısında.|  
|[CFindReplaceDialog::GetReplaceString](#getreplacestring)|Geçerli değiştirme dizesini almak için bu işlevini çağırın.|  
|[CFindReplaceDialog::IsTerminating](#isterminating)|İletişim kutusu sonlandırma olup olmadığını belirlemek için bu işlevini çağırın.|  
|[CFindReplaceDialog::MatchCase](#matchcase)|Kullanıcı Bul dizesinin tam olarak harf istediği olup olmadığını belirlemek için bu işlevini çağırın.|  
|[CFindReplaceDialog::MatchWholeWord](#matchwholeword)|Kullanıcının yalnızca tüm sözcükleri eşleştirmeye istediği olup olmadığını belirlemek için bu işlevini çağırın.|  
|[CFindReplaceDialog::ReplaceAll](#replaceall)|Kullanıcının değiştirilecek dizenin tüm oluşumlarını istediği olup olmadığını belirlemek için bu işlevini çağırın.|  
|[CFindReplaceDialog::ReplaceCurrent](#replacecurrent)|Kullanıcının değiştirilecek geçerli sözcüğü istediği olup olmadığını belirlemek için bu işlevini çağırın.|  
|[CFindReplaceDialog::SearchDown](#searchdown)|Kullanıcı aşağı yönde devam etmek için arama isteyip istemediğini belirlemek için bu işlevini çağırın.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CFindReplaceDialog::m_fr](#m_fr)|Özelleştirmek için kullanılan bir yapı bir `CFindReplaceDialog` nesnesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Diğer Windows ortak iletişim kutuları, aksine `CFindReplaceDialog` nesneleri geçici ekranda durumdayken diğer windows ile etkileşime girmesine izin verme. İki tür vardır, `CFindReplaceDialog` nesneleri: Bul iletişim kutuları ve iletişim kutularında bulun ve değiştirin. İletişim kutuları giriş arama ve arama/değiştirme dizeleri kullanıcıya izin verse de, bunlar herhangi bir arama veya İşlevler değiştirme gerçekleştirmeyin. Bu uygulamaya eklemeniz gerekir.  
  
 Oluşturmak için bir `CFindReplaceDialog` nesne, (bağımsız değişkenler olan) sağlanan bir oluşturucu kullanın. Kalıcı olmayan iletişim kutusu olduğundan yığın kullanma nesne tahsis **yeni** işleci yerine yığında.  
  
 Bir kez bir `CFindReplaceDialog` nesne oluşturulan, çağırmalısınız [oluşturma](#create) oluşturmak ve iletişim kutusunu görüntülemek için üye işlevi.  
  
 Kullanım [m_fr](#m_fr) çağırmadan önce iletişim kutusu başlatılamadı yapısı `Create`. `m_fr` Yapısıdır türü [FINDREPLACE](http://msdn.microsoft.com/library/windows/desktop/ms646835). Bu yapı hakkında daha fazla bilgi için Windows SDK'sı bakın.  
  
 Bulma/değiştirme isteklerinin bildirim almak üst penceresinin sırayla Windows kullanmalısınız [RegisterWindowMessage](http://msdn.microsoft.com/library/windows/desktop/ms644947) işlev ve kullanmak [on_regıstered_message](message-map-macros-mfc.md#on_registered_message) , çerçevesinde ileti eşleme makrosu kayıtlı bu iletiyi işleyen penceresini açın.  
  
 Kullanıcı iletişim kutusuyla sonlandırmak karar olup olmadığını belirlemek `IsTerminating` üye işlevi.  
  
 `CFindReplaceDialog` üzerinde COMMDLG kullanır. Windows 3.1 ve sonraki sürümleri ile birlikte gelen DLL dosyası.  
  
 Özelleştir iletişim kutusu için bir sınıf türetin `CFindReplaceDialog`, özel iletişim şablonu sağlayın ve genişletilmiş denetimlerden bildirim iletilerini işlemek için ileti eşlemesi ekleyin. İşlenmemiş tüm iletiler için temel sınıf geçirilmesi gerekir.  
  
 Kanca işlevini özelleştirme gerekli değildir.  
  
 Kullanma hakkında daha fazla bilgi için `CFindReplaceDialog`, bkz: [ortak iletişim kutusu sınıfları](../../mfc/common-dialog-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `CFindReplaceDialog`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdlgs.h  
  
##  <a name="cfindreplacedialog"></a>  CFindReplaceDialog::CFindReplaceDialog  
 Oluşturan bir `CFindReplaceDialog` nesnesi.  
  
```  
CFindReplaceDialog();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çünkü `CFindReplaceDialog` nesne bir kalıcı olmayan iletişim kutusu, kullanarak da öbekte oluşturmalıdır **yeni** işleci.  
  
 Yok etme sırasında framework gerçekleştirmeye bir **bu silme** iletişim kutusu işaretçisine üzerinde. İletişim kutusu yığında oluşturduysanız **bu** işaretçi yok ve tanımsız davranışa neden olabilir.  
  
 Oluşturma işlemi hakkında daha fazla bilgi için `CFindReplaceDialog` nesneleri bkz [CFindReplaceDialog](../../mfc/reference/cfindreplacedialog-class.md) genel bakış. Kullanım [CFindReplaceDialog::Create](#create) iletişim kutusunu görüntülemek için üye işlevi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#170](../../mfc/codesnippet/cpp/cfindreplacedialog-class_1.cpp)]  
  
##  <a name="create"></a>  CFindReplaceDialog::Create  
 Oluşturur ve Bul veya Bul ve Değiştir iletişim kutusu nesnesi, değerine bağlı olarak görüntüler `bFindDialogOnly`.  
  
```  
virtual BOOL Create(
    BOOL bFindDialogOnly,  
    LPCTSTR lpszFindWhat,  
    LPCTSTR lpszReplaceWith = NULL,  
    DWORD dwFlags = FR_DOWN,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 *bFindDialogOnly*  
 Bu parametre kümesine `TRUE` görüntülemek için bir **Bul** iletişim kutusu. Ayarlamak `FALSE` görüntülemek için bir **bulun ve değiştirin** iletişim kutusu.  
  
 *lpszFindWhat*  
 İletişim kutusu görüntülendiğinde, varsayılan arama dizesi işaretçi. Varsa `NULL`, iletişim kutusunda varsayılan arama dizesi içermiyor.  
  
 *lpszReplaceWith*  
 İletişim kutusu görüntülendiğinde varsayılan değiştirme dizesini işaretçi. Varsa `NULL`, iletişim kutusunda varsayılan değiştirme dizesi içermiyor.  
  
 *dwFlags*  
 Bit düzeyinde OR işleci kullanılarak birleştirilen iletişim kutusu ayarlarını özelleştirmek için kullanabileceğiniz bir veya daha fazla bayraklar. Varsayılan değer `FR_DOWN`, arama aşağıya bir yönde devam etmek için olduğunu belirtir. Bkz: [FINDREPLACE](http://msdn.microsoft.com/library/windows/desktop/ms646835) bu bayrakları hakkında daha fazla bilgi için Windows SDK'sı yapısında.  
  
 *pParentWnd*  
 İletişim kutusunun üst veya sahibi penceresi için bir işaretçi. Bu bulma/değiştirme eylemi istenip istenmediğini belirten özel iletiyi alacak penceredir. Varsa `NULL`, uygulamanın ana penceresi kullanılır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İletişim kutusu nesnesi başarıyla oluşturulduysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bulma/değiştirme isteklerinin bildirim almak üst penceresinin sırayla Windows kullanmalısınız [RegisterWindowMessage](http://msdn.microsoft.com/library/windows/desktop/ms644947) işlevi dönüş değeri olan uygulamanın örneğine benzersiz bir ileti numarası. Çerçeve penceresi geri çağırma işlevi bildiren bir ileti eşleme girişi olmalıdır ( `OnFindReplace` aşağıdaki örnekte) kayıtlı bu iletiyi işler. Aşağıdaki kod parçası adlı bir çerçeve pencere sınıfı için bunu nasıl örneğidir `CMyRichEditView`:  
  
 [!code-cpp[NVC_MFCDocView#171](../../mfc/codesnippet/cpp/cfindreplacedialog-class_2.h)]  
  
 [!code-cpp[NVC_MFCDocView#172](../../mfc/codesnippet/cpp/cfindreplacedialog-class_3.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#173](../../mfc/codesnippet/cpp/cfindreplacedialog-class_4.cpp)]  
  
 İçinde `OnFindReplace` işlevini kullanarak kullanıcı amaçları yorumlama [CFindReplaceDialog::FindNext](#findnext) ve [CFindReplaceDialog::IsTerminating](#isterminating) yöntemler ve kod oluşturma bulma/değiştirme işlemleri için.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CFindReplaceDialog::CFindReplaceDialog](#cfindreplacedialog).  
  
##  <a name="findnext"></a>  CFindReplaceDialog::FindNext  
 Bu işlev kullanıcının arama dizesi Sonrakini Bul istediği olup olmadığını belirlemek için geri çağırma işlevini çağırın.  
  
```  
BOOL FindNext() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kullanıcı arama dizesi Sonrakini Bul istiyorsa, sıfır olmayan; Aksi takdirde 0.  
  
##  <a name="getfindstring"></a>  CFindReplaceDialog::GetFindString  
 Bu işlev bulmak için varsayılan dizesini almak için geri çağırma işlevini çağırın.  
  
```  
CString GetFindString() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bulmak için varsayılan dizesi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#69](../../mfc/codesnippet/cpp/cfindreplacedialog-class_5.cpp)]  
  
##  <a name="getnotifier"></a>  CFindReplaceDialog::GetNotifier  
 Geçerli Bul Değiştir iletişim kutusu için bir işaretçi almak için bu işlevini çağırın.  
  
```  
static CFindReplaceDialog* PASCAL GetNotifier(LPARAM lParam);
```  
  
### <a name="parameters"></a>Parametreler  
 *lParam*  
 **Lparam** çerçeve pencere için geçirilen değer **OnFindReplace** üye işlevi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli iletişim kutusu için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Geri çağırma işlevi içerisinde kullanılmalı geçerli iletişim kutusuna erişmek için onun üye işlevleri ve erişim çağırın `m_fr` yapısı.  
  
### <a name="example"></a>Örnek  
 Bkz: [CFindReplaceDialog::Create](#create) Bul Değiştir iletişim kutusundan bildirimleri almak için OnFindReplace işleyici kaydetme ilişkin bir örnek.  
  
 [!code-cpp[NVC_MFCDocView#69](../../mfc/codesnippet/cpp/cfindreplacedialog-class_5.cpp)]  
  
##  <a name="getreplacestring"></a>  CFindReplaceDialog::GetReplaceString  
 Geçerli değiştirme dizesini almak için bu işlevini çağırın.  
  
```  
CString GetReplaceString() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Hangi bulunan dizeleri değiştirmek varsayılan dizesi.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CFindReplaceDialog::GetFindString](#getfindstring).  
  
##  <a name="isterminating"></a>  CFindReplaceDialog::IsTerminating  
 Kullanıcı iletişim kutusu sonlandırmak karar olup olmadığını belirlemek için geri çağırma işlevi içinde bu işlevini çağırın.  
  
```  
BOOL IsTerminating() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kullanıcı iletişim kutusu sonlandırmak karar verdiyse sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlevi sıfır olmayan bir değer döndürürse, çağırmalıdır `DestroyWindow` geçerli iletişim kutusu ve herhangi bir iletişim kutusu işaretçi değişkeninin kümesi üye işlevini **NULL**. İsteğe bağlı olarak, ayrıca son girilen bulun ve değiştirin metni depolamak ve sonraki Bul ve Değiştir iletişim kutusunu başlatmak için kullanın.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CFindReplaceDialog::GetFindString](#getfindstring).  
  
##  <a name="m_fr"></a>  CFindReplaceDialog::m_fr  
 Özelleştirmek için kullanılan bir `CFindReplaceDialog` nesnesi.  
  
```  
FINDREPLACE m_fr;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 `m_fr` bir yapıdır türü [FINDREPLACE](http://msdn.microsoft.com/library/windows/desktop/ms646835). Üyeleri iletişim kutusu nesnesinin özelliklerini depolar. Oluşturma sonrasında bir `CFindReplaceDialog` nesne kullanabileceğiniz `m_fr` iletişim kutusundaki çeşitli değerleri değiştirmek için.  
  
 Bu yapı hakkında daha fazla bilgi için bkz: **FINDREPLACE** Windows SDK'sındaki yapısı.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CFindReplaceDialog::CFindReplaceDialog](#cfindreplacedialog).  
  
##  <a name="matchcase"></a>  CFindReplaceDialog::MatchCase  
 Kullanıcı Bul dizesinin tam olarak harf istediği olup olmadığını belirlemek için bu işlevini çağırın.  
  
```  
BOOL MatchCase() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tam arama dizesi büyük küçük harf duyarlı arama dizesi örneklerini bulmak kullanıcı istiyorsa, sıfır olmayan; Aksi takdirde 0.  
  
##  <a name="matchwholeword"></a>  CFindReplaceDialog::MatchWholeWord  
 Kullanıcının yalnızca tüm sözcükleri eşleştirmeye istediği olup olmadığını belirlemek için bu işlevini çağırın.  
  
```  
BOOL MatchWholeWord() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kullanıcı arama dizesi, yalnızca tüm sözcükleri eşleştirmeye isterse sıfır olmayan; Aksi takdirde 0.  
  
##  <a name="replaceall"></a>  CFindReplaceDialog::ReplaceAll  
 Kullanıcının değiştirilecek dizenin tüm oluşumlarını istediği olup olmadığını belirlemek için bu işlevini çağırın.  
  
```  
BOOL ReplaceAll() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kullanıcı Değiştir dize eşleşen tüm dizeleri değiştirilmesi istediyseniz sıfır olmayan; Aksi takdirde 0.  
  
##  <a name="replacecurrent"></a>  CFindReplaceDialog::ReplaceCurrent  
 Kullanıcının değiştirilecek geçerli sözcüğü istediği olup olmadığını belirlemek için bu işlevini çağırın.  
  
```  
BOOL ReplaceCurrent() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kullanıcı şu anda seçili dizeyi Değiştir dizesi ile değiştirilmesi istediyseniz sıfır olmayan; Aksi takdirde 0.  
  
##  <a name="searchdown"></a>  CFindReplaceDialog::SearchDown  
 Kullanıcı aşağı yönde devam etmek için arama isteyip istemediğini belirlemek için bu işlevini çağırın.  
  
```  
BOOL SearchDown() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kullanıcı aşağı yönde devam etmek için arama isterse sıfır olmayan; Kullanıcı bir yukarı yönde devam etmek için arama isterse 0.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CCommonDialog sınıfı](../../mfc/reference/ccommondialog-class.md)   
 [Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)  
