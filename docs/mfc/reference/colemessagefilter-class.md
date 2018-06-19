---
title: COleMessageFilter sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleMessageFilter
- AFXOLE/COleMessageFilter
- AFXOLE/COleMessageFilter::COleMessageFilter
- AFXOLE/COleMessageFilter::BeginBusyState
- AFXOLE/COleMessageFilter::EnableBusyDialog
- AFXOLE/COleMessageFilter::EnableNotRespondingDialog
- AFXOLE/COleMessageFilter::EndBusyState
- AFXOLE/COleMessageFilter::OnMessagePending
- AFXOLE/COleMessageFilter::Register
- AFXOLE/COleMessageFilter::Revoke
- AFXOLE/COleMessageFilter::SetBusyReply
- AFXOLE/COleMessageFilter::SetMessagePendingDelay
- AFXOLE/COleMessageFilter::SetRetryReply
dev_langs:
- C++
helpviewer_keywords:
- COleMessageFilter [MFC], COleMessageFilter
- COleMessageFilter [MFC], BeginBusyState
- COleMessageFilter [MFC], EnableBusyDialog
- COleMessageFilter [MFC], EnableNotRespondingDialog
- COleMessageFilter [MFC], EndBusyState
- COleMessageFilter [MFC], OnMessagePending
- COleMessageFilter [MFC], Register
- COleMessageFilter [MFC], Revoke
- COleMessageFilter [MFC], SetBusyReply
- COleMessageFilter [MFC], SetMessagePendingDelay
- COleMessageFilter [MFC], SetRetryReply
ms.assetid: b1fd1639-fac4-4fd0-bf17-15172deba13c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 85161e7f3dd752c6df27afedf6276f8823e7ec6e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33371370"
---
# <a name="colemessagefilter-class"></a>COleMessageFilter sınıfı
OLE uygulamaları etkileşim tarafından gerekli eşzamanlılık yönetir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class COleMessageFilter : public CCmdTarget  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleMessageFilter::COleMessageFilter](#colemessagefilter)|Oluşturan bir `COleMessageFilter` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleMessageFilter::BeginBusyState](#beginbusystate)|Uygulama meşgul durumda koyar.|  
|[COleMessageFilter::EnableBusyDialog](#enablebusydialog)|Adlı bir uygulama meşgul iletişim kutusu görüntülendiğinde devre dışı bırakır ve sağlar.|  
|[COleMessageFilter::EnableNotRespondingDialog](#enablenotrespondingdialog)|Adlı bir uygulama yanıt iletişim kutusu görüntülendiğinde devre dışı bırakır ve sağlar.|  
|[COleMessageFilter::EndBusyState](#endbusystate)|Uygulamanın meşgul durum sonlandırır.|  
|[COleMessageFilter::OnMessagePending](#onmessagepending)|OLE çağrı sürerken iletilerini işlemek için çerçevesi tarafından çağrılır.|  
|[COleMessageFilter::Register](#register)|İleti Filtresi OLE sistem DLL'leri ile kaydeder.|  
|[COleMessageFilter::Revoke](#revoke)|OLE sistem DLL'leri ileti filtrenin kaydı iptal eder.|  
|[COleMessageFilter::SetBusyReply](#setbusyreply)|OLE çağrısı meşgul uygulamanın Yanıtla belirler.|  
|[COleMessageFilter::SetMessagePendingDelay](#setmessagependingdelay)|Uygulama bir OLE çağrısının yanıtı ne kadar bekleyeceğini belirler.|  
|[COleMessageFilter::SetRetryReply](#setretryreply)|Meşgul bir uygulamayı çağıran uygulamanın Yanıtla belirler.|  
  
## <a name="remarks"></a>Açıklamalar  
 `COleMessageFilter` Sınıfı, görsel düzenleme sunucu ve kapsayıcı uygulamaları, aynı zamanda OLE Otomasyon uygulamaları yararlıdır. Çağrılan sunucu uygulamaları için bu sınıf, böylece diğer kapsayıcı uygulamalardan gelen çağrıları iptal ya da daha sonra yeniden uygulamayı "meşgul" yapmak için kullanılabilir. Bu sınıf, çağıran bir uygulama tarafından çağrılan uygulama meşgul olduğunda gerçekleştirilecek eylemi belirlemek için de kullanılabilir.  
  
 Ortak kullanımdır çağırmak bir sunucu uygulaması için [BeginBusyState](#beginbusystate) ve [EndBusyState](#endbusystate) zaman onu bir belge veya yok edilmesi için diğer OLE erişilebilir nesne için tehlikeli olabilir. Bu çağrı içinde yapılan [CWinApp::OnIdle](../../mfc/reference/cwinapp-class.md#onidle) kullanıcı arabirimi güncelleştirmeleri sırasında.  
  
 Varsayılan olarak, bir `COleMessageFilter` nesne, uygulama başlatıldığında ayrılır. İle alınabilir [AfxOleGetMessageFilter](application-control.md#afxolegetmessagefilter).  
  
 Bu gelişmiş bir sınıftır; nadiren ile doğrudan çalışmak için gerekir.  
  
 Daha fazla bilgi için bkz: [sunucular: sunucu uygulama](../../mfc/servers-implementing-a-server.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleMessageFilter`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxole.h  
  
##  <a name="beginbusystate"></a>  COleMessageFilter::BeginBusyState  
 Meşgul durum başlamak için bu işlevini çağırın.  
  
```  
virtual void BeginBusyState();
```  
  
### <a name="remarks"></a>Açıklamalar  
 İle birlikte çalışır [EndBusyState](#endbusystate) uygulamanın meşgul durumunu denetlemek için. İşlev [SetBusyReply](#setbusyreply) meşgul olduğunda uygulamalar için uygulama yanıt belirler.  
  
 `BeginBusyState` Ve `EndBusyState` çağrıları artırmak ve sırasıyla uygulama meşgul olup olmadığını belirleyen bir sayaç azaltma. Örneğin, iki çağrılar `BeginBusyState` ve yapılan bir çağrı `EndBusyState` hala meşgul durum sonuçlanır. Çağrı için gerekli olduğu bir meşgul durumu iptal etmek için `EndBusyState` aynı kaç kez `BeginBusyState` çağrıldı.  
  
 Varsayılan olarak, framework tarafından gerçekleştirilen boşta işleme sırasında meşgul durumuna girer [CWinApp::OnIdle](../../mfc/reference/cwinapp-class.md#onidle). Uygulama işleme sırasında **ON_COMMANDUPDATEUI** bildirimleri, gelen çağrıları boşta işleme işlemi tamamlandıktan sonra daha sonra işlenir.  
  
##  <a name="colemessagefilter"></a>  COleMessageFilter::COleMessageFilter  
 Oluşturur bir `COleMessageFilter` nesnesi.  
  
```  
COleMessageFilter();
```  
  
##  <a name="enablebusydialog"></a>  COleMessageFilter::EnableBusyDialog  
 İleti bekleyen gecikme süresi dolduğunda görüntülenen meşgul iletişim kutusu devre dışı bırakır ve sağlar (bkz [SetRetryReply](#setretryreply)) OLE çağrısı sırasında.  
  
```  
void EnableBusyDialog(BOOL bEnableBusy = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 *bEnableBusy*  
 "Meşgul" iletişim kutusunu etkin mi yoksa devre dışı mı olduğunu belirtir.  
  
##  <a name="enablenotrespondingdialog"></a>  COleMessageFilter::EnableNotRespondingDialog  
 Sağlar ve bir klavye veya fare ileti bekleme durumundaysa görüntülenen "vermiyor" iletişim kutusunu devre dışı bırakan bir OLE sırasında çağrısı ve çağrı zaman aşımına uğradı.  
  
```  
void EnableNotRespondingDialog(BOOL bEnableNotResponding = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 *bEnableNotResponding*  
 "Vermiyor" iletişim kutusu etkin mi yoksa devre dışı mı olduğunu belirtir.  
  
##  <a name="endbusystate"></a>  COleMessageFilter::EndBusyState  
 Meşgul durum sonlandırmak için bu işlevini çağırın.  
  
```  
virtual void EndBusyState();
```  
  
### <a name="remarks"></a>Açıklamalar  
 İle birlikte çalışır [BeginBusyState](#beginbusystate) uygulamanın meşgul durumunu denetlemek için. İşlev [SetBusyReply](#setbusyreply) meşgul olduğunda uygulamalar için uygulama yanıt belirler.  
  
 `BeginBusyState` Ve `EndBusyState` çağrıları artırmak ve sırasıyla uygulama meşgul olup olmadığını belirleyen bir sayaç azaltma. Örneğin, iki çağrılar `BeginBusyState` ve yapılan bir çağrı `EndBusyState` hala meşgul durum sonuçlanır. Çağrı için gerekli olduğu bir meşgul durumu iptal etmek için `EndBusyState` aynı kaç kez `BeginBusyState` çağrıldı.  
  
 Varsayılan olarak, framework tarafından gerçekleştirilen boşta işleme sırasında meşgul durumuna girer [CWinApp::OnIdle](../../mfc/reference/cwinapp-class.md#onidle). Uygulama işleme sırasında `ON_UPDATE_COMMAND_UI` bildirimleri, gelen çağrıları boşta işleme işlemi tamamlandıktan sonra işlenir.  
  
##  <a name="onmessagepending"></a>  COleMessageFilter::OnMessagePending  
 OLE çağrı sürerken iletilerini işlemek için çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL OnMessagePending(const MSG* pMsg);
```  
  
### <a name="parameters"></a>Parametreler  
 `pMsg`  
 İşaretçi bekleyen iletisi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarı sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağıran bir uygulama bir çağrı tamamlanması beklenirken framework çağırması `OnMessagePending` bekleyen iletisi işaretçiyle. Varsayılan olarak, framework gönderir `WM_PAINT` iletileri böylece penceresi güncelleştirmeleri uzun sürüyor bir çağrı sırasında ortaya çıkabilir.  
  
 Çağrı yoluyla İleti Filtresi kaydetmelisiniz [kaydetmek](#register) etkin olabilmesi için önce.  
  
##  <a name="register"></a>  COleMessageFilter::Register  
 İleti Filtresi OLE sistem DLL'leri ile kaydeder.  
  
```  
BOOL Register();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarı sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 DLL'leri sistemiyle kaydedilmemişse İleti Filtresi bir etkisi yoktur. Genellikle, uygulamanızın başlatma kodunu uygulamanın İleti Filtresi kaydeder. Program için bir çağrı tarafından bitirmeden uygulamanız tarafından kaydedilen diğer İleti Filtresi çağrılması gereken [iptal](#revoke).  
  
 Framework'ün varsayılan İleti Filtresi otomatik olarak başlatma sırasında kayıtlı ve sonlandırmanın iptal edildi.  
  
##  <a name="revoke"></a>  COleMessageFilter::Revoke  
 Bir çağrı tarafından gerçekleştirilen bir önceki kayıt iptal [kaydetmek](#register).  
  
```  
void Revoke();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir ileti filtresi, program sonlandırılmadan önce iptal edilmesi gerekir.  
  
 Oluşturuluyor ve otomatik olarak çerçevesi tarafından varsayılan ileti filtresi da otomatik olarak iptal edilir.  
  
##  <a name="setbusyreply"></a>  COleMessageFilter::SetBusyReply  
 Bu işlev uygulamanın "meşgul yanıt." ayarlar  
  
```  
void SetBusyReply(SERVERCALL nBusyReply);
```  
  
### <a name="parameters"></a>Parametreler  
 *nBusyReply*  
 Arasında bir değer `SERVERCALL` COMPOBJ içinde tanımlanan numaralandırması. H. Aşağıdaki değerlerden biri olabilir:  
  
- **SERVERCALL_ISHANDLED** uygulama çağrıları kabul edebilirsiniz, ancak belirli bir çağrı işlenirken başarısız olabilir.  
  
- **SERVERCALL_REJECTED** uygulama büyük olasılıkla hiçbir zaman bir çağrıyı işlemek mümkün olacaktır.  
  
- **SERVERCALL_RETRYLATER** uygulama geçici bir durumda bir çağrı işleyemiyor durumda.  
  
### <a name="remarks"></a>Açıklamalar  
 [BeginBusyState](#beginbusystate) ve [EndBusyState](#endbusystate) işlevleri denetleyen uygulamanın meşgul durumu.  
  
 Ne zaman bir uygulama yapılan bir çağrı ile meşgul `BeginBusyState`, son ayarı tarafından belirlenen bir değerle OLE sistem DLL'leri çağrıları yanıt `SetBusyReply`. Çağrı yapan uygulamanın bu meşgul yanıtı hangi eylemin yapılacağını belirlemek için kullanır.  
  
 Varsayılan olarak, meşgul yanıt olan **SERVERCALL_RETRYLATER**. Bu yanıt çağrı mümkün olan en kısa sürede yeniden denemek çağrı yapan uygulamanın neden olur.  
  
##  <a name="setmessagependingdelay"></a>  COleMessageFilter::SetMessagePendingDelay  
 Çağrı yapan uygulamanın daha fazla eylemi gerçekleştirmeden önce çağrılan uygulamasından bir yanıt ne kadar bekleyeceğini belirler.  
  
```  
void SetMessagePendingDelay(DWORD nTimeout = 5000);
```  
  
### <a name="parameters"></a>Parametreler  
 `nTimeout`  
 İleti bekleyen gecikme için milisaniye sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev ile birlikte çalışır [SetRetryReply](#setretryreply).  
  
##  <a name="setretryreply"></a>  COleMessageFilter::SetRetryReply  
 Adlı bir uygulamadan meşgul yanıtı aldığında, çağıran uygulamanın eylem belirler.  
  
```  
void SetRetryReply(DWORD nRetryReply = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 `nRetryReply`  
 Denemeler arasındaki milisaniye sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Adlı bir uygulama meşgul olduğunu gösteriyorsa, çağıran uygulama sunucu artık, hemen yeniden deneyin ya da belirtilen bir zaman aralığından sonra yeniden denemek için meşgul kadar beklemeniz karar verebilirsiniz. Çağrı tamamen iptal etmek de karar verebilirsiniz.  
  
 Çağıranın yanıt işlevleri tarafından denetlenen `SetRetryReply` ve [SetMessagePendingDelay](#setmessagependingdelay). `SetRetryReply` Belirtilen arama için yeniden denemeler arasında çağrı yapan uygulamanın ne kadar beklemesi gerektiğini belirler. `SetMessagePendingDelay` Çağrı yapan uygulamanın sunucudan yanıt daha fazla eylemi gerçekleştirmeden önce bekleyeceği süreyi belirler.  
  
 Genellikle Varsayılanları kabul edilir ve değiştirilmesi gerekmez. Framework çağrı yeniden deneme her `nRetryReply` çağrı geçtiği veya ileti bekleyen gecikme süresi dolmuş kadar milisaniye. İçin 0 değerini `nRetryReply` hemen bir yeniden deneme ve - 1 çağrı iptali belirtir.  
  
 Ne zaman iletisi bekleyen gecikme süresi doldu, OLE "meşgul iletişim kutusu" (bkz [COleBusyDialog](../../mfc/reference/colebusydialog-class.md)) kullanıcı iptal etmek veya çağrı yeniden denemek seçebilmeniz görüntülenir. Çağrı [EnableBusyDialog](#enablebusydialog) etkinleştirin veya bu iletişim kutusunu devre dışı bırakmak için.  
  
 Klavye veya fare bir ileti olduğunda bekleyen bir çağrı ve çağrı sırasında zaman aşımına uğradı (ileti bekleyen gecikme aşıldı), "vermiyor" iletişim kutusu görüntülenir. Çağrı [EnableNotRespondingDialog](#enablenotrespondingdialog) etkinleştirin veya bu iletişim kutusunu devre dışı bırakmak için. Genellikle bu durumu, bir şeyler yanlış geçti ve kullanıcı sabırsız alma gösterir.  
  
 İletişim kutuları devre dışı bırakıldığında geçerli "yeniden deneme yanıt" her zaman çağrılar yoğun uygulamalar için kullanılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CCmdTarget sınıfı](../../mfc/reference/ccmdtarget-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CCmdTarget Sınıfı](../../mfc/reference/ccmdtarget-class.md)
