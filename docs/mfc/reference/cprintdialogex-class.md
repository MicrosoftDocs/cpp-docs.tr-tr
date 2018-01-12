---
title: "CPrintDialogEx sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPrintDialogEx
- AFXDLGS/CPrintDialogEx
- AFXDLGS/CPrintDialogEx::CPrintDialogEx
- AFXDLGS/CPrintDialogEx::CreatePrinterDC
- AFXDLGS/CPrintDialogEx::DoModal
- AFXDLGS/CPrintDialogEx::GetCopies
- AFXDLGS/CPrintDialogEx::GetDefaults
- AFXDLGS/CPrintDialogEx::GetDeviceName
- AFXDLGS/CPrintDialogEx::GetDevMode
- AFXDLGS/CPrintDialogEx::GetDriverName
- AFXDLGS/CPrintDialogEx::GetPortName
- AFXDLGS/CPrintDialogEx::GetPrinterDC
- AFXDLGS/CPrintDialogEx::PrintAll
- AFXDLGS/CPrintDialogEx::PrintCollate
- AFXDLGS/CPrintDialogEx::PrintCurrentPage
- AFXDLGS/CPrintDialogEx::PrintRange
- AFXDLGS/CPrintDialogEx::PrintSelection
- AFXDLGS/CPrintDialogEx::m_pdex
dev_langs: C++
helpviewer_keywords:
- CPrintDialogEx [MFC], CPrintDialogEx
- CPrintDialogEx [MFC], CreatePrinterDC
- CPrintDialogEx [MFC], DoModal
- CPrintDialogEx [MFC], GetCopies
- CPrintDialogEx [MFC], GetDefaults
- CPrintDialogEx [MFC], GetDeviceName
- CPrintDialogEx [MFC], GetDevMode
- CPrintDialogEx [MFC], GetDriverName
- CPrintDialogEx [MFC], GetPortName
- CPrintDialogEx [MFC], GetPrinterDC
- CPrintDialogEx [MFC], PrintAll
- CPrintDialogEx [MFC], PrintCollate
- CPrintDialogEx [MFC], PrintCurrentPage
- CPrintDialogEx [MFC], PrintRange
- CPrintDialogEx [MFC], PrintSelection
- CPrintDialogEx [MFC], m_pdex
ms.assetid: 1d506703-ee1c-44cc-b4ce-4e778fec26b8
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 147a3d638f76f291a9732b340335331730f5b74d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cprintdialogex-class"></a>CPrintDialogEx sınıfı
Windows 2000 yazdırma özellik sayfası tarafından sağlanan hizmetlerin yalıtır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CPrintDialogEx : public CCommonDialog  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CPrintDialogEx::CPrintDialogEx](#cprintdialogex)|Oluşturan bir `CPrintDialogEx` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CPrintDialogEx::CreatePrinterDC](#createprinterdc)|Yazdır iletişim kutusu görüntülenmeden yazıcı cihaz bağlamı oluşturur.|  
|[CPrintDialogEx::DoModal](#domodal)|İletişim kutusu görüntüler ve kullanıcının seçim yapmanızı sağlar.|  
|[CPrintDialogEx::GetCopies](#getcopies)|İstenen kopya sayısını alır.|  
|[CPrintDialogEx::GetDefaults](#getdefaults)|Cihaz Varsayılanları iletişim kutusu görüntülenmeden alır.|  
|[CPrintDialogEx::GetDeviceName](#getdevicename)|Şu anda seçili yazıcı aygıtının adını alır.|  
|[CPrintDialogEx::GetDevMode](#getdevmode)|Alır `DEVMODE` yapısı.|  
|[CPrintDialogEx::GetDriverName](#getdrivername)|Sistem tarafından tanımlanan yazıcı aygıt sürücüsünün adını alır.|  
|[CPrintDialogEx::GetPortName](#getportname)|Şu anda seçili yazıcı bağlantı noktasını adını alır.|  
|[CPrintDialogEx::GetPrinterDC](#getprinterdc)|Yazıcı cihaz bağlamı için bir tanıtıcı alır.|  
|[CPrintDialogEx::PrintAll](#printall)|Belgenin tüm sayfaları yazdırmak belirler.|  
|[CPrintDialogEx::PrintCollate](#printcollate)|Harmanlanmış kopya istenen belirler.|  
|[CPrintDialogEx::PrintCurrentPage](#printcurrentpage)|Belge geçerli sayfa yazdırmak belirler.|  
|[CPrintDialogEx::PrintRange](#printrange)|Belirtilen aralığını sayfa yazdırmak belirler.|  
|[CPrintDialogEx::PrintSelection](#printselection)|Yalnızca seçili öğeleri yazdırmak belirler.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CPrintDialogEx::m_pdex](#m_pdex)|Özelleştirmek için kullanılan bir yapı bir `CPrintDialogEx` nesnesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Yazdırma işlemi, uygulamanız için pek çok görünüşünün işlemek için çerçevesi güvenebilirsiniz. Yazdırma görevlerini işlemek için framework kullanma hakkında daha fazla bilgi için bkz: [yazdırma](../../mfc/printing.md).  
  
 Framework'ün katılımı olmadan yazdırma işlemek için uygulamanızın istiyorsanız kullanabileceğiniz `CPrintDialogEx` sağlanan Oluşturucusu ile "olduğu gibi" sınıf ya da kendi iletişim sınıfından türetilen `CPrintDialogEx` ve gereksinimlerinize uygun olarak bir oluşturucu yazma. Sınıfından türetilen her iki durumda da, bu iletişim kutularından standart MFC iletişim kutuları gibi davranacak `CCommonDialog`.  
  
 Kullanılacak bir `CPrintDialogEx` nesne, öncelikle nesnesini kullanarak oluşturmanız `CPrintDialogEx` Oluşturucusu. İletişim kutusu oluşturulan sonra ayarlamak veya herhangi bir değer değiştirmek [m_pdex](#m_pdex) yapısı, iletişim kutusunun denetimlerinin değerlerini başlatılamadı. `m_pdex` Yapısıdır türü [PRINTDLGEX](http://msdn.microsoft.com/library/windows/desktop/ms646844). Bu yapı hakkında daha fazla bilgi için Windows SDK'sı bakın.  
  
 Kendi tanıtıcıları belirtmezseniz `m_pdex` için **hDevMode** ve **hDevNames** üyeleri, Windows işlevi çağırma özen **GlobalFree** bu tanıtıcıları için iletişim kutusu tamamladığınızda.  
  
 İletişim kutusu denetimleri başlatılıyor sonra çağrı `DoModal` üye işlevi iletişim kutusunu görüntülemek ve yazdırma seçeneklerini seçmek kullanıcı izin vermek için. Zaman `DoModal` döndürür, kullanıcı Tamam, Uygula veya iptal düğmesi seçili olup olmadığını belirleyebilir.  
  
 Kullanıcı Tamam basıldıysa kullanabileceğiniz `CPrintDialogEx`ait kullanıcı tarafından giriş bilgilerini almak için üye işlevleri.  
  
 `CPrintDialogEx::GetDefaults` Üye işlevi geçerli yazıcı Varsayılanları iletişim kutusu görüntülenmeden almak için yararlıdır. Bu yöntem, kullanıcı etkileşimi gerektirir.  
  
 Windows kullanabilirsiniz **CommDlgExtendedError** işlevi iletişim kutusunu başlatma sırasında bir hata olup olmadığını belirlemek ve hata hakkında daha fazla bilgi için. Bu işlev hakkında daha fazla bilgi için Windows SDK'sı bakın.  
  
 Kullanma hakkında daha fazla bilgi için `CPrintDialogEx`, bkz: [ortak iletişim kutusu sınıfları](../../mfc/common-dialog-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 `IObjectWithSite`  
  
 `IPrintDialogCallback`  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `CPrintDialogEx`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdlgs.h  
  
##  <a name="cprintdialogex"></a>CPrintDialogEx::CPrintDialogEx  
 Bir Windows 2000 yazdırma özellik sayfası oluşturur.  
  
```  
CPrintDialogEx(
    DWORD dwFlags = PD_ALLPAGES | PD_USEDEVMODECOPIES | PD_NOPAGENUMS       | PD_HIDEPRINTTOFILE | PD_NOSELECTION | PD_NOCURRENTPAGE,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwFlags`  
 Bit düzeyinde OR işleci kullanılarak birleştirilen iletişim kutusu ayarlarını özelleştirmek için kullanabileceğiniz bir veya daha fazla bayraklar. Örneğin, **PD_ALLPAGES** bayrağını belgenin tüm sayfalar için varsayılan yazdırma aralığı ayarlar. Bkz: [PRINTDLGEX](http://msdn.microsoft.com/library/windows/desktop/ms646844) bu bayrakları hakkında daha fazla bilgi için Windows SDK'sı yapısında.  
  
 `pParentWnd`  
 İletişim kutusunun üst veya sahibi penceresi için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi yalnızca nesnesi oluşturur. Kullanım `DoModal` iletişim kutusunu görüntülemek için üye işlevi.  
  
##  <a name="createprinterdc"></a>CPrintDialogEx::CreatePrinterDC  
 Bir yazıcı cihaz bağlamı (DC) oluşturur [aygıt MODUNDAN](http://msdn.microsoft.com/library/windows/desktop/dd183565) ve [DEVNAMES](../../mfc/reference/devnames-structure.md) yapıları.  
  
```  
HDC CreatePrinterDC();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeni oluşturulan yazıcı cihaz bağlamına işleyin.  
  
### <a name="remarks"></a>Açıklamalar  
 Döndürülen etki alanı denetleyicisi aynı zamanda depolanan **hDC** üyesi [m_pdex](#m_pdex).  
  
 Bu DC geçerli yazıcı DC olduğu varsayılır ve daha önce edindiğiniz diğer yazıcı DC'leri silinmesi gerekir. Bu işlev çağrılır ve Yazdır iletişim kutusu görüntülemeden elde edilen etki alanı denetleyicisi kullanılır.  
  
##  <a name="domodal"></a>CPrintDialogEx::DoModal  
 Windows 2000 Ortak yazdırma özellik sayfasını görüntüleyin ve kopyalar, sayfa aralığı sayısı gibi çeşitli yazdırma seçeneklerini seçmek kullanıcı izin vermek için bu işlevi çağırmak ve kopya Harmanlanmış.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 INT_PTR dönüş değeri gerçekte bir HRESULT:. Dönüş değerleri bölümüne bakın [PrintDlgEx](http://msdn.microsoft.com/library/windows/desktop/ms646942) Windows SDK'sındaki.  
  
### <a name="remarks"></a>Açıklamalar  
 Üyeleri ayarlayarak çeşitli yazdırma iletişim seçenekleri başlatmak istiyorsanız `m_pdex` yapısı, bu çağırmadan önce yapmanız gerektiğini `DoModal`, ancak iletişim nesnesi oluşturulur.  
  
 Çağırdıktan sonra `DoModal`, diğer üye ayarları veya kullanıcı tarafından bilgi giriş iletişim kutusuna almak için işlevleri çağırabilir.  
  
 Varsa **PD_RETURNDC** bayrağı çağrılırken kullanılan `DoModal`, yazıcı DC içinde döndürülen **hDC** üyesi [m_pdex](#m_pdex). Bu DC çağrısıyla boşaltılması [DeleteDC](http://msdn.microsoft.com/library/windows/desktop/dd183533) çağıran tarafından `CPrintDialogEx`.  
  
##  <a name="getcopies"></a>CPrintDialogEx::GetCopies  
 Bu işlev çağrısı çağrıldıktan sonra `DoModal` istenen kopya sayısı alınamadı.  
  
```  
int GetCopies() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İstenen kopya sayısı.  
  
##  <a name="getdefaults"></a>CPrintDialogEx::GetDefaults  
 Bir iletişim kutusu görüntülenmeden varsayılan yazıcının cihaz Varsayılanları almak için bu işlevini çağırın.  
  
```  
BOOL GetDefaults();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 **DOĞRU** başarılı olursa, aksi takdirde **FALSE**.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir yazıcı cihaz bağlamı (DC) oluşturur [aygıt MODUNDAN](http://msdn.microsoft.com/library/windows/desktop/dd183565) ve [DEVNAMES](../../mfc/reference/devnames-structure.md) yapıları.  
  
 `GetDefaults`Yazdırma özellik sayfası görüntülenmez. Bunun yerine, ayarlar **hDevNames** ve **hDevMode** üyeleri [m_pdex](#m_pdex) tanıtıcıları için [aygıt MODUNDAN](http://msdn.microsoft.com/library/windows/desktop/dd183565) ve [DEVNAMES ](../../mfc/reference/devnames-structure.md) için sistem varsayılan yazıcı başlatılmış yapıları. Her ikisi de **hDevNames** ve **hDevMode** NULL olmalıdır veya `GetDefaults` başarısız olur.  
  
 Varsa **PD_RETURNDC** bayrağı ayarlanmış, bu işlevi değil yalnızca döndürülecek **hDevNames** ve **hDevMode** (bulunan **m_pdex.hDevNames** ve **m_pdex.hDevMode**) çağırana, ancak aynı zamanda bir yazıcıya DC döndürür **m_pdex.hDC**. Yazıcı DC silme ve Windows çağırmak için arayan sorumluluğundadır [GlobalFree](http://msdn.microsoft.com/library/windows/desktop/aa366579) işlevi ile işiniz bittiğinde tanıtıcıları üzerinde `CPrintDialogEx` nesnesi.  
  
##  <a name="getdevicename"></a>CPrintDialogEx::GetDeviceName  
 Bu işlev çağrısı çağrıldıktan sonra [DoModal](#domodal) şu anda seçili yazıcının veya çağırdıktan sonra adı almak için [GetDefaults](#getdefaults) varsayılan yazıcının adını almak için.  
  
```  
CString GetDeviceName() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Seçili yazıcının adı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir işaretçi kullanmak `CString` tarafından döndürülen nesne `GetDeviceName` değeri olarak `lpszDeviceName` çağrıda [CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc).  
  
##  <a name="getdevmode"></a>CPrintDialogEx::GetDevMode  
 Bu işlev çağrısı çağrıldıktan sonra [DoModal](#domodal) veya [GetDefaults](#getdefaults) yazdırma aygıtı hakkında bilgi almak için.  
  
```  
LPDEVMODE GetDevMode() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 [Aygıt MODUNDAN](http://msdn.microsoft.com/library/windows/desktop/dd183565) aygıt başlatma ve bir yazıcı sürücüsü ortamı hakkında bilgi içeren veri yapısı. Bu yapı Windows tarafından gerçekleştirilecek bellek kilidini açmanız gerekir [GlobalUnlock](http://msdn.microsoft.com/library/windows/desktop/aa366595) Windows SDK'ın açıklanan işlevi.  
  
##  <a name="getdrivername"></a>CPrintDialogEx::GetDriverName  
 Bu işlev çağrısı çağrıldıktan sonra [DoModal](#domodal) veya [GetDefaults](#getdefaults) sistem tarafından tanımlanan yazıcı aygıt sürücüsünün adını almak için.  
  
```  
CString GetDriverName() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `CString` sistem tarafından tanımlanan sürücü adı belirtme.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir işaretçi kullanmak `CString` tarafından döndürülen nesne `GetDriverName` değeri olarak `lpszDriverName` çağrıda [CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc).  
  
##  <a name="getportname"></a>CPrintDialogEx::GetPortName  
 Bu işlev çağrısı çağrıldıktan sonra [DoModal](#domodal) veya [GetDefaults](#getdefaults) şu anda seçili yazıcı bağlantı noktası adı alınamadı.  
  
```  
CString GetPortName() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Şu anda seçili yazıcı bağlantı noktası adı.  
  
##  <a name="getprinterdc"></a>CPrintDialogEx::GetPrinterDC  
 Yazıcı cihaz bağlamı için bir işleyici döner.  
  
```  
HDC GetPrinterDC() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yazıcı cihaz bağlamı için bir tanıtıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 Windows çağırmalısınız [DeleteDC](http://msdn.microsoft.com/library/windows/desktop/dd183533) işiniz bittiğinde cihaz bağlamı silmek için işlevi kullanıyor.  
  
##  <a name="m_pdex"></a>CPrintDialogEx::m_pdex  
 Üyeleri iletişim nesnesinin özelliklerini depolamak PRINTDLGEX yapısı.  
  
```  
PRINTDLGEX m_pdex;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturma sonrasında bir `CPrintDialogEx` nesne kullanabileceğiniz `m_pdex` çağırmadan önce iletişim kutusu çeşitli yönlerini ayarlamak için [DoModal](#domodal) üye işlevi. Daha fazla bilgi için `m_pdex` yapısı için bkz: [PRINTDLGEX](http://msdn.microsoft.com/library/windows/desktop/ms646844) Windows SDK'sındaki.  
  
 Değiştirirseniz `m_pdex` veri üyesi doğrudan herhangi varsayılan davranışı geçersiz kılar.  
  
##  <a name="printall"></a>CPrintDialogEx::PrintAll  
 Bu işlev çağrısı çağrıldıktan sonra `DoModal` belgedeki tüm sayfaları yazdırmak karar vermek için.  
  
```  
BOOL PrintAll() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 **DOĞRU** yazdırılan; tersi durumda belgedeki tüm sayfaların olması durumunda **FALSE**.  
  
##  <a name="printcollate"></a>CPrintDialogEx::PrintCollate  
 Bu işlev çağrısı çağrıldıktan sonra `DoModal` yazıcı belgenin yazdırılan tüm kopyalarını collate olup olmadığını belirlemek için.  
  
```  
BOOL PrintCollate() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 **DOĞRU** kullanıcı iletişim kutusundaki; collate onay kutusunu seçerse aksi **FALSE**.  
  
##  <a name="printcurrentpage"></a>CPrintDialogEx::PrintCurrentPage  
 Bu işlev çağrısı çağrıldıktan sonra `DoModal` belgedeki geçerli sayfa yazdırmak karar vermek için.  
  
```  
BOOL PrintCurrentPage() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 **DOĞRU** varsa **geçerli sayfa yazdırma** yazdırma iletişim kutusunda seçili; Aksi takdirde **FALSE**.  
  
##  <a name="printrange"></a>CPrintDialogEx::PrintRange  
 Bu işlev çağrısı çağrıldıktan sonra `DoModal` belgedeki sayfaları yalnızca bir dizi yazdırmak karar vermek için.  
  
```  
BOOL PrintRange() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 **DOĞRU** belgedeki sayfa aralığı yalnızca yazdırılan; tersi durumda **FALSE**.  
  
### <a name="remarks"></a>Açıklamalar  
 Belirtilen sayfa aralıklarını gelen belirlenebilir [m_pdex](#m_pdex) (bkz **nPageRanges**, **nMaxPageRanges**, ve **lpPageRanges** içinde[ PRINTDLGEX](http://msdn.microsoft.com/library/windows/desktop/ms646844) Windows SDK'sı yapısında).  
  
##  <a name="printselection"></a>CPrintDialogEx::PrintSelection  
 Bu işlev çağrısı çağrıldıktan sonra `DoModal` yalnızca şu anda seçili öğeleri yazdırmak karar vermek için.  
  
```  
BOOL PrintSelection() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 **DOĞRU** seçili öğeleri yazdırılan; tersi durumda, yalnızca **FALSE**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CCommonDialog sınıfı](../../mfc/reference/ccommondialog-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CPrintInfo Yapısı](../../mfc/reference/cprintinfo-structure.md)
