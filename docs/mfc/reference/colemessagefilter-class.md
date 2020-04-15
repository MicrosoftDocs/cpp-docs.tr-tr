---
title: COleMessageFilter Sınıfı
ms.date: 11/04/2016
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
ms.openlocfilehash: f6db5f012aedf08edd87980e304e181295bfb953
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374921"
---
# <a name="colemessagefilter-class"></a>COleMessageFilter Sınıfı

OLE uygulamalarının etkileşimi için gerekli eşzamanlılığı yönetir.

## <a name="syntax"></a>Sözdizimi

```
class COleMessageFilter : public CCmdTarget
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[COleMessageFiltresi::COleMessageFiltresi](#colemessagefilter)|Bir `COleMessageFilter` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[COleMessageFiltre::BeginBusyState](#beginbusystate)|Uygulamayı meşgul durumuna getirir.|
|[COleMessageFilter::EnableBusyDialog](#enablebusydialog)|Çağrılan bir uygulama meşgul olduğunda görünen iletişim kutusunu etkinleştirir ve devre dışı kılabilir.|
|[COleMessageFilter::EnableNotRespondingDialog](#enablenotrespondingdialog)|Çağrılan bir uygulama yanıt vermiyorsa görünen iletişim kutusunu etkinleştirir ve devre dışı kılabilir.|
|[COleMessageFiltresi::EndBusyState](#endbusystate)|Uygulamanın meşgul durumunu sona erdirir.|
|[COleMessageFilter::OnMessagePending](#onmessagepending)|OLE çağrısı devam ederken iletileri işlemek için çerçeve tarafından çağrılır.|
|[COleMessageFilter::Kayıt](#register)|İleti filtresini OLE sistemi DL'lerine kaydeder.|
|[COleMessageFilter::İptal](#revoke)|İleti filtresinin OLE sistemi DL'leri ile kaydını iptal eder.|
|[COleMessageFiltresi::SetBusyReply](#setbusyreply)|Meşgul uygulamanın Bir OLE çağrısına yanıtını belirler.|
|[COleMessageFiltresi::SetMessagePendingDelay](#setmessagependingdelay)|Uygulamanın Bir OLE çağrısına yanıt için ne kadar bekleyeceğini belirler.|
|[COleMessageFiltresi::SetRetryYanıtla](#setretryreply)|Arama uygulamasının meşgul bir uygulamaya yanıtını belirler.|

## <a name="remarks"></a>Açıklamalar

Sınıf, `COleMessageFilter` görsel düzenleme sunucusu ve kapsayıcı uygulamalarının yanı sıra OLE otomasyon uygulamalarında da yararlıdır. Çağrılan sunucu uygulamaları için, bu sınıf uygulamayı "meşgul" yapmak için kullanılabilir, böylece diğer kapsayıcı uygulamalarından gelen çağrılar iptal edilir veya daha sonra yeniden denenmiştir. Bu sınıf, çağrılan uygulama meşgul olduğunda bir arama uygulaması tarafından yapılacak eylemi belirlemek için de kullanılabilir.

Bir sunucu uygulamasının, bir belgenin veya diğer OLE erişilebilir nesnenin yok edilmesinin tehlikeli olacağı durumlarda [BeginBusyState](#beginbusystate) ve [EndBusyState'i](#endbusystate) araması yaygın olarak kullanılabilir. Bu aramalar [CWinApp::OnIdle](../../mfc/reference/cwinapp-class.md#onidle) kullanıcı arabirimi güncellemeleri sırasında yapılır.

Varsayılan olarak, `COleMessageFilter` uygulama baş harfe çevrilir bir nesne ayrılır. [AfxOleGetMessageFilter](application-control.md#afxolegetmessagefilter)ile alınabilir.

Bu gelişmiş bir sınıftır; nadiren doğrudan çalışmak gerekir.

Daha fazla bilgi için, makale [Sunucular bakın: Bir Sunucu uygulama.](../../mfc/servers-implementing-a-server.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

`COleMessageFilter`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxole.h

## <a name="colemessagefilterbeginbusystate"></a><a name="beginbusystate"></a>COleMessageFiltre::BeginBusyState

Meşgul bir durum başlatmak için bu işlevi arayın.

```
virtual void BeginBusyState();
```

### <a name="remarks"></a>Açıklamalar

Uygulamanın yoğun durumunu denetlemek için [EndBusyState](#endbusystate) ile birlikte çalışır. [SetBusyReply](#setbusyreply) işlevi, meşgul olduğunda uygulamanın arama uygulamalarına yanıtını belirler.

Ve `BeginBusyState` `EndBusyState` sırasıyla artış ve karar çağırır, uygulama meşgul olup olmadığını belirleyen bir sayaç. Örneğin, iki arama `BeginBusyState` ve bir `EndBusyState` arama hala meşgul bir durum neden. Meşgul bir durumu iptal etmek `EndBusyState` için aynı sayıda `BeginBusyState` kez çağrılması gerekir.

Varsayılan olarak, çerçeve CWinApp tarafından gerçekleştirilen boşta işleme sırasında meşgul durumuna [girer::OnIdle](../../mfc/reference/cwinapp-class.md#onidle). Uygulama bildirimleri ON_COMMANDUPDATEUI işlerken, boşta işleme tamamlandıktan sonra gelen aramalar daha sonra işlenir.

## <a name="colemessagefiltercolemessagefilter"></a><a name="colemessagefilter"></a>COleMessageFiltresi::COleMessageFiltresi

Bir `COleMessageFilter` nesnesi oluşturur.

```
COleMessageFilter();
```

## <a name="colemessagefilterenablebusydialog"></a><a name="enablebusydialog"></a>COleMessageFilter::EnableBusyDialog

İleti bekleyen gecikme süresi dolduğunda görüntülenen meşgul iletişim kutusunu etkinleştirir ve devre dışı katanır (Bkz. OLE çağrısı sırasında [SetRetryReply).](#setretryreply)

```
void EnableBusyDialog(BOOL bEnableBusy = TRUE);
```

### <a name="parameters"></a>Parametreler

*bEnableBusy*<br/>
"Meşgul" iletişim kutusunun etkin mi yoksa devre dışı mı olduğunu belirtir.

## <a name="colemessagefilterenablenotrespondingdialog"></a><a name="enablenotrespondingdialog"></a>COleMessageFilter::EnableNotRespondingDialog

OLE çağrısı sırasında klavye veya fare iletisi beklemedeyse ve arama zaman dolduysa görüntülenen "yanıt vermiyor" iletişim kutusunu etkinleştirer ve devre dışı katanır.

```
void EnableNotRespondingDialog(BOOL bEnableNotResponding = TRUE);
```

### <a name="parameters"></a>Parametreler

*bEnableNotResponding*<br/>
"Yanıt vermiyor" iletişim kutusunun etkin mi yoksa devre dışı mı bırakıldığını belirtir.

## <a name="colemessagefilterendbusystate"></a><a name="endbusystate"></a>COleMessageFiltresi::EndBusyState

Yoğun bir durumu sona erdirmek için bu işlevi çağırın.

```
virtual void EndBusyState();
```

### <a name="remarks"></a>Açıklamalar

Uygulamanın yoğun durumunu denetlemek için [BeginBusyState](#beginbusystate) ile birlikte çalışır. [SetBusyReply](#setbusyreply) işlevi, meşgul olduğunda uygulamanın arama uygulamalarına yanıtını belirler.

Ve `BeginBusyState` `EndBusyState` sırasıyla artış ve karar çağırır, uygulama meşgul olup olmadığını belirleyen bir sayaç. Örneğin, iki arama `BeginBusyState` ve bir `EndBusyState` arama hala meşgul bir durum neden. Meşgul bir durumu iptal etmek `EndBusyState` için aynı sayıda `BeginBusyState` kez çağrılması gerekir.

Varsayılan olarak, çerçeve CWinApp tarafından gerçekleştirilen boşta işleme sırasında meşgul durumuna [girer::OnIdle](../../mfc/reference/cwinapp-class.md#onidle). Uygulama bildirimleri ON_UPDATE_COMMAND_UI işlerken, boşta işleme tamamlandıktan sonra gelen aramalar işlenir.

## <a name="colemessagefilteronmessagepending"></a><a name="onmessagepending"></a>COleMessageFilter::OnMessagePending

OLE çağrısı devam ederken iletileri işlemek için çerçeve tarafından çağrılır.

```
virtual BOOL OnMessagePending(const MSG* pMsg);
```

### <a name="parameters"></a>Parametreler

*pMsg*<br/>
Bekleyen iletiiçin işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız başarı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bir arama uygulaması bir aramanın tamamlanmasını bekliyorsa, çerçeve bekleyen iletiye işaretçiyle çağırır. `OnMessagePending` Varsayılan olarak, çerçeve WM_PAINT iletileri gönderir, böylece pencere güncelleştirmeleri uzun zaman alan bir arama sırasında oluşabilir.

İleti filtrenizi, etkin hale gelmeden önce [Kaydolmak](#register) için bir çağrı yoluyla kaydetmeniz gerekir.

## <a name="colemessagefilterregister"></a><a name="register"></a>COleMessageFilter::Kayıt

İleti filtresini OLE sistemi DL'lerine kaydeder.

```
BOOL Register();
```

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız başarı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

İleti filtresi, sistem DL'lerine kayıtlı olmadığı sürece hiçbir etkisi yoktur. Genellikle uygulamanızın başlatma kodu uygulamanın ileti filtresini kaydeder. Uygulamanız tarafından kaydedilmiş diğer ileti filtresi, program [iptal](#revoke)etme çağrısıyla sona ermeden önce iptal edilmelidir.

Çerçevenin varsayılan ileti filtresi başlatma sırasında otomatik olarak kaydedilir ve sonlandırma sırasında iptal edilir.

## <a name="colemessagefilterrevoke"></a><a name="revoke"></a>COleMessageFilter::İptal

[Kaydolmak](#register)için yapılan bir çağrı yla gerçekleştirilen önceki bir kaydı iptal eder.

```
void Revoke();
```

### <a name="remarks"></a>Açıklamalar

Program sona ermeden önce bir ileti filtresi iptal edilmelidir.

Çerçeve tarafından oluşturulan ve otomatik olarak kaydedilen varsayılan ileti filtresi de otomatik olarak iptal edilir.

## <a name="colemessagefiltersetbusyreply"></a><a name="setbusyreply"></a>COleMessageFiltresi::SetBusyReply

Bu işlev, uygulamanın "meşgul yanıtını" ayarlar.

```
void SetBusyReply(SERVERCALL nBusyReply);
```

### <a name="parameters"></a>Parametreler

*nBusyReply*<br/>
COMPOBJ'de tanımlanan numaralandırmadan `SERVERCALL` bir değer. H. Aşağıdaki değerlerden herhangi birine sahip olabilir:

- SERVERCALL_ISHANDLED Uygulama aramaları kabul edebilir, ancak belirli bir aramayı işleme de başarısız olabilir.

- SERVERCALL_REJECTED Uygulama büyük olasılıkla bir aramayı asla işleyemeyecektir.

- SERVERCALL_RETRYLATER Uygulama geçici olarak bir aramayı işleyemeyeceği bir durumdadır.

### <a name="remarks"></a>Açıklamalar

[BeginBusyState](#beginbusystate) ve [EndBusyState](#endbusystate) işlevleri uygulamanın meşgul durumunu denetler.

Bir uygulama bir çağrı ile meşgul `BeginBusyState`yapıldığında , o ole sistemi DLs gelen aramalara son ayarı tarafından belirlenen bir değer ile yanıt `SetBusyReply`verir. Arama uygulaması, hangi eylemin gerçekleşsüreceğini belirlemek için bu meşgul yanıtı kullanır.

Varsayılan olarak, meşgul yanıtı SERVERCALL_RETRYLATER. Bu yanıt, arama uygulamasının aramayı mümkün olan en kısa sürede yeniden denemesine neden olur.

## <a name="colemessagefiltersetmessagependingdelay"></a><a name="setmessagependingdelay"></a>COleMessageFiltresi::SetMessagePendingDelay

Arama uygulamasının daha fazla eylem yapmadan önce çağrılan uygulamadan yanıt için ne kadar bekleyeceğini belirler.

```
void SetMessagePendingDelay(DWORD nTimeout = 5000);
```

### <a name="parameters"></a>Parametreler

*nTimeout*<br/>
İleti bekleyen gecikme için milisaniye sayısı.

### <a name="remarks"></a>Açıklamalar

Bu fonksiyon [SetRetryReply](#setretryreply)ile birlikte çalışır.

## <a name="colemessagefiltersetretryreply"></a><a name="setretryreply"></a>COleMessageFiltresi::SetRetryYanıtla

Çağrılan bir uygulamadan yoğun yanıt aldığında arama uygulamasının eylemini belirler.

```
void SetRetryReply(DWORD nRetryReply = 0);
```

### <a name="parameters"></a>Parametreler

*nRetryYanıtla*<br/>
Yeniden denemeler arasında milisaniye sayısı.

### <a name="remarks"></a>Açıklamalar

Çağrılan bir uygulama meşgul olduğunu gösterdiğinde, arama uygulaması sunucunun artık meşgul olmamasını, hemen yeniden denemesini veya belirli bir aradan sonra yeniden denemesini beklemeye karar verebilir. Ayrıca aramayı tamamen iptal etmeye karar verebilir.

Arayanın yanıtı işlevler `SetRetryReply` ve [SetMessagePendingDelay](#setmessagependingdelay)tarafından denetlenir. `SetRetryReply`arama uygulamasının belirli bir arama için yeniden denemeler arasında ne kadar beklemesi gerektiğini belirler. `SetMessagePendingDelay`arama uygulamasının daha fazla işlem yapmadan önce sunucudan yanıt almayı ne kadar beklediğini belirler.

Genellikle varsayılanlar kabul edilebilir ve değiştirilmesi gerekmez. Çerçeve, arama geçene veya ileti bekleyen gecikme süresi dolana kadar her *nRetryReply* milisaniye aramasını yeniden dener. *nRetryReply* için 0 değeri hemen yeniden deneme belirtir ve - 1 aramanın iptalini belirtir.

İleti bekleyen gecikme süresi dolduğunda, kullanıcının aramayı iptal etmeyi veya yeniden denemeyi seçebilmeleri için OLE "meşgul iletişim kutusu" [(COleBusyDialog'a](../../mfc/reference/colebusydialog-class.md)bakın) görüntülenir. Bu iletişim kutusunu etkinleştirmek veya devre dışı kakmak için [EnableBusyDialog'u](#enablebusydialog) arayın.

Arama sırasında klavye veya fare iletisi beklemedeyken ve arama zaman aşımına uğradı (ileti bekleyen gecikmeyi aştı), "yanıt vermiyor" iletişim kutusu görüntülenir. Bu iletişim kutusunu etkinleştirmek veya devre dışı kakmak için [EnableNotRespondingDialog'u](#enablenotrespondingdialog) arayın. Genellikle bu durum bir şeylerin ters gittiğini ve kullanıcının sabırsızlaştığını gösterir.

İletişim araçları devre dışı bırakıldığında, geçerli "yeniden deneme yanıtı" her zaman meşgul uygulamalara yapılan aramalar için kullanılır.

## <a name="see-also"></a>Ayrıca bkz.

[CCmdTarget Sınıfı](../../mfc/reference/ccmdtarget-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CCmdTarget Sınıfı](../../mfc/reference/ccmdtarget-class.md)
