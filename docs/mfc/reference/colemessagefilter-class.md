---
description: 'Daha fazla bilgi edinin: Cotamessagefilter sınıfı'
title: Cotamessagefilter sınıfı
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
ms.openlocfilehash: f0ab1d473704f5355933c04072a195c12fb71c73
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97226902"
---
# <a name="colemessagefilter-class"></a>Cotamessagefilter sınıfı

OLE uygulamalarının etkileşimi için gereken eşzamanlılık düzeyini yönetir.

## <a name="syntax"></a>Syntax

```
class COleMessageFilter : public CCmdTarget
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Copamessagefilter:: Cotamessagefilter](#colemessagefilter)|Bir `COleMessageFilter` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Cotamessagefilter:: BeginBusyState](#beginbusystate)|Uygulamayı meşgul durumuna geçirir.|
|[Cotamessagefilter:: EnableBusyDialog](#enablebusydialog)|Çağrılan bir uygulama meşgulse görüntülenen iletişim kutusunu etkinleştirilir ve devre dışı bırakır.|
|[Cotamessagefilter:: EnableNotRespondingDialog](#enablenotrespondingdialog)|Çağrılan bir uygulama yanıt vermediğinde görüntülenen iletişim kutusunu etkinleştirilir ve devre dışı bırakır.|
|[Cotamessagefilter:: EndBusyState](#endbusystate)|Uygulamanın meşgul durumunu sonlandırır.|
|[Cotamessagefilter:: OnMessagePending](#onmessagepending)|Bir OLE çağrısı sürerken iletileri işlemek için çerçeve tarafından çağırılır.|
|[Cotamessagefilter:: Register](#register)|İleti filtresini OLE sistem dll 'Leriyle kaydeder.|
|[Cotamessagefilter:: Revoke](#revoke)|OLE sistem dll 'Leriyle ileti filtresinin kaydını iptal eder.|
|[Cotamessagefilter:: SetBusyReply](#setbusyreply)|Meşgul uygulamanın bir OLE çağrısı yanıtı belirler.|
|[Cotamessagefilter:: SetMessagePendingDelay](#setmessagependingdelay)|Uygulamanın OLE çağrısının yanıtını ne kadar bekleyeceğini belirler.|
|[Cotamessagefilter:: SetRetryReply](#setretryreply)|Çağıran uygulamanın meşgul bir uygulamaya yönelik yanıtı belirler.|

## <a name="remarks"></a>Açıklamalar

`COleMessageFilter`Sınıfı, Visual Editing Server ve kapsayıcı uygulamalarında ve OLE Otomasyonu uygulamalarında yararlı olur. Çağrılan sunucu uygulamaları için bu sınıf, diğer kapsayıcı uygulamalardan gelen çağrıların iptal edilmesi veya daha sonra yeniden deneneceği şekilde uygulamayı "meşgul" yapmak için kullanılabilir. Bu sınıf, çağrılan uygulama meşgul olduğunda çağıran bir uygulama tarafından gerçekleştirilecek eylemi tespit etmek için de kullanılabilir.

Yaygın kullanım, bir sunucu uygulamasının bir belge veya başka bir OLE erişilebilir nesnenin yok edilmesi için tehlikeli olması durumunda [beginbusimstate](#beginbusystate) ve [endbusi durumunu](#endbusystate) çağırması için kullanılır. Bu çağrılar, Kullanıcı Arabirimi güncelleştirmeleri sırasında [CWinApp:: OnIdle](../../mfc/reference/cwinapp-class.md#onidle) içinde yapılır.

Varsayılan olarak, `COleMessageFilter` uygulama başlatıldığında bir nesne ayrılır. Bu, [AfxOleGetMessageFilter](application-control.md#afxolegetmessagefilter)ile alınabilir.

Bu gelişmiş bir sınıftır; nadiren doğrudan bunlarla çalışmanız gerekir.

Daha fazla bilgi için bkz. [sunucular: sunucu uygulama](../../mfc/servers-implementing-a-server.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`COleMessageFilter`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxole. h

## <a name="colemessagefilterbeginbusystate"></a><a name="beginbusystate"></a> Cotamessagefilter:: BeginBusyState

Meşgul durumuna başlamak için bu işlevi çağırın.

```
virtual void BeginBusyState();
```

### <a name="remarks"></a>Açıklamalar

Uygulamanın meşgul durumunu denetlemek için [Endbuso durumu](#endbusystate) ile birlikte çalışarak. [Setbusyıreply](#setbusyreply) işlevi, uygulamanın meşgul olduğunda uygulamaları çağırma yanıtı belirler.

`BeginBusyState`Ve, `EndBusyState` uygulamanın meşgul olup olmadığını belirleyen bir sayaç sırasıyla artış ve azaltma ' yı çağırır. Örneğin, iki çağrı `BeginBusyState` ve bir çağrı `EndBusyState` hala meşgul durumuna neden olabilir. Meşgul durumunu iptal etmek için `EndBusyState` aynı sayıda çağrılması gerekir `BeginBusyState` .

Varsayılan olarak, çerçeve, [CWinApp:: OnIdle](../../mfc/reference/cwinapp-class.md#onidle)tarafından gerçekleştirilen boşta işleme sırasında meşgul durumuna girer. Uygulama ON_COMMANDUPDATEUI bildirimlerini işlerken, boşta işleme tamamlandıktan sonra gelen çağrılar daha sonra işlenir.

## <a name="colemessagefiltercolemessagefilter"></a><a name="colemessagefilter"></a> Copamessagefilter:: Cotamessagefilter

Bir `COleMessageFilter` nesnesi oluşturur.

```
COleMessageFilter();
```

## <a name="colemessagefilterenablebusydialog"></a><a name="enablebusydialog"></a> Cotamessagefilter:: EnableBusyDialog

Bir OLE çağrısı sırasında ileti bekleyen gecikme süresi dolarsa (bkz. [SetRetryReply](#setretryreply)), meşgul iletişim kutusunu etkinleştirilir ve devre dışı bırakır.

```cpp
void EnableBusyDialog(BOOL bEnableBusy = TRUE);
```

### <a name="parameters"></a>Parametreler

*Zararsız*<br/>
"Meşgul" iletişim kutusunun etkin veya devre dışı olduğunu belirtir.

## <a name="colemessagefilterenablenotrespondingdialog"></a><a name="enablenotrespondingdialog"></a> Cotamessagefilter:: EnableNotRespondingDialog

OLE çağrısı sırasında bir klavye veya fare iletisi beklenirse ve çağrı zaman aşımına uğradığından, "yanıt vermiyor" iletişim kutusunu etkinleştirilir ve devre dışı bırakır.

```cpp
void EnableNotRespondingDialog(BOOL bEnableNotResponding = TRUE);
```

### <a name="parameters"></a>Parametreler

*Benablenotyanýt*<br/>
"Yanıt vermiyor" iletişim kutusunun etkin veya devre dışı olduğunu belirtir.

## <a name="colemessagefilterendbusystate"></a><a name="endbusystate"></a> Cotamessagefilter:: EndBusyState

Meşgul durumu sonlandırmak için bu işlevi çağırın.

```
virtual void EndBusyState();
```

### <a name="remarks"></a>Açıklamalar

Uygulamanın meşgul durumunu denetlemek için [Beginbuso durumu](#beginbusystate) ile birlikte çalışarak. [Setbusyıreply](#setbusyreply) işlevi, uygulamanın meşgul olduğunda uygulamaları çağırma yanıtı belirler.

`BeginBusyState`Ve, `EndBusyState` uygulamanın meşgul olup olmadığını belirleyen bir sayaç sırasıyla artış ve azaltma ' yı çağırır. Örneğin, iki çağrı `BeginBusyState` ve bir çağrı `EndBusyState` hala meşgul durumuna neden olabilir. Meşgul durumunu iptal etmek için `EndBusyState` aynı sayıda çağrılması gerekir `BeginBusyState` .

Varsayılan olarak, çerçeve, [CWinApp:: OnIdle](../../mfc/reference/cwinapp-class.md#onidle)tarafından gerçekleştirilen boşta işleme sırasında meşgul durumuna girer. Uygulama ON_UPDATE_COMMAND_UI bildirimlerini işlerken, boşta işleme tamamlandıktan sonra gelen çağrılar işlenir.

## <a name="colemessagefilteronmessagepending"></a><a name="onmessagepending"></a> Cotamessagefilter:: OnMessagePending

Bir OLE çağrısı sürerken iletileri işlemek için çerçeve tarafından çağırılır.

```
virtual BOOL OnMessagePending(const MSG* pMsg);
```

### <a name="parameters"></a>Parametreler

*pMsg*<br/>
Bekleyen ileti işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Sıfırdan farklı, başarılı olma; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Çağıran bir uygulama bir çağrının tamamlanmasını beklerken, çerçeve `OnMessagePending` bekleyen ileti işaretçisi ile çağırır. Varsayılan olarak, çerçeve WM_PAINT iletileri dağıtır ve bu sayede, uzun süren bir çağrı sırasında pencere güncelleştirmelerinin gerçekleşebilmesini sağlayabilirsiniz.

İleti filtrenizi, etkin hale gelmeden önce [kaydolma](#register) çağrısı yoluyla kaydetmeniz gerekir.

## <a name="colemessagefilterregister"></a><a name="register"></a> Cotamessagefilter:: Register

İleti filtresini OLE sistem dll 'Leriyle kaydeder.

```
BOOL Register();
```

### <a name="return-value"></a>Dönüş Değeri

Sıfırdan farklı, başarılı olma; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bir ileti filtresinin, sistem dll 'Lerine kaydedilmedikleri takdirde hiçbir etkisi yoktur. Genellikle uygulamanızın başlatma kodu uygulamanın ileti filtresini kaydeder. Uygulama tarafından kaydedilen diğer herhangi bir ileti filtresi, program [Iptal etme](#revoke)çağrısıyla sona ermeden önce iptal edilmelidir.

Çerçevenin varsayılan ileti filtresi başlatma sırasında otomatik olarak kaydedilir ve sonlandırıldığında iptal edilir.

## <a name="colemessagefilterrevoke"></a><a name="revoke"></a> Cotamessagefilter:: Revoke

[Kayıt](#register)çağrısı tarafından gerçekleştirilen önceki kaydı iptal eder.

```cpp
void Revoke();
```

### <a name="remarks"></a>Açıklamalar

Program sonlandırılmadan önce bir ileti filtresi iptal edilmelidir.

Çerçeve tarafından otomatik olarak oluşturulan ve kaydedilen varsayılan ileti filtresi de otomatik olarak iptal edilir.

## <a name="colemessagefiltersetbusyreply"></a><a name="setbusyreply"></a> Cotamessagefilter:: SetBusyReply

Bu işlev, uygulamanın "meşgul yanıtı" olarak ayarlar.

```cpp
void SetBusyReply(SERVERCALL nBusyReply);
```

### <a name="parameters"></a>Parametreler

*Nbusyıreply*<br/>
`SERVERCALL`Sabit listesinden COMPOBJ. H içinde tanımlanan bir değer. Aşağıdaki değerlerden herhangi biri olabilir:

- SERVERCALL_ISHANDLED uygulama çağrıları kabul edebilir, ancak belirli bir çağrıyı işlerken başarısız olabilir.

- Uygulama SERVERCALL_REJECTED muhtemelen bir çağrıyı işleyemeyecektir.

- SERVERCALL_RETRYLATER uygulama geçici olarak bir çağrıyı işleyebileceği bir durumda.

### <a name="remarks"></a>Açıklamalar

[Beginbusi](#beginbusystate) State ve [endbusi State](#endbusystate) işlevleri uygulamanın meşgul durumunu denetler.

Bir uygulama bir çağrısıyla meşgul olduğunda `BeginBusyState` , bu, son ayarıyla belirlenen bir değere sahıp OLE sistem dll 'lerinden yapılan çağrılara yanıt verir `SetBusyReply` . Çağıran uygulama, hangi eylemin yapılacağını belirlemek için bu meşgul yanıtı kullanır.

Varsayılan olarak, meşgul yanıtı SERVERCALL_RETRYLATER. Bu yanıt çağıran uygulamanın çağrıyı mümkün olan en kısa sürede yeniden denemesini sağlar.

## <a name="colemessagefiltersetmessagependingdelay"></a><a name="setmessagependingdelay"></a> Cotamessagefilter:: SetMessagePendingDelay

Çağıran uygulamanın, başka bir işlem yapmadan önce çağrılan uygulamadan bir Yanıt beklemesi gereken süreyi belirler.

```cpp
void SetMessagePendingDelay(DWORD nTimeout = 5000);
```

### <a name="parameters"></a>Parametreler

*nTimeout*<br/>
İleti bekleyen gecikme süresi için milisaniye sayısı.

### <a name="remarks"></a>Açıklamalar

Bu işlev, [SetRetryReply](#setretryreply)ile konser 'de çalışır.

## <a name="colemessagefiltersetretryreply"></a><a name="setretryreply"></a> Cotamessagefilter:: SetRetryReply

Çağrılan uygulamadan meşgul yanıtı aldığında çağıran uygulamanın eylemini belirler.

```cpp
void SetRetryReply(DWORD nRetryReply = 0);
```

### <a name="parameters"></a>Parametreler

*nRetryReply*<br/>
Yeniden denemeler arasındaki milisaniye sayısı.

### <a name="remarks"></a>Açıklamalar

Çağrılan bir uygulama meşgul olduğunu gösteriyorsa, çağıran uygulama, sunucunun artık meşgul olmaması, hemen yeniden denenmesinin veya belirtilen bir aralıktan sonra yeniden denenene kadar beklemeye karar verebilir. Ayrıca, çağrıyı tamamen iptal etmeyi de karar verebilir.

Arayanın yanıtı, `SetRetryReply` ve [SetMessagePendingDelay](#setmessagependingdelay)işlevleri tarafından denetlenir. `SetRetryReply` çağıran uygulamanın belirli bir çağrının yeniden denemeler arasında ne kadar süre beklemesi gerektiğini belirler. `SetMessagePendingDelay` çağıran uygulamanın, başka bir işlem yapmadan önce sunucudan yanıt bekleyeceği süreyi belirler.

Genellikle varsayılanlar kabul edilebilir olur ve değiştirilmesi gerekmez. Çerçeve, çağrı tamamlanana veya ileti bekleyen gecikme süresi sona erene kadar her *nRetryReply* milisaniyesi çağrısını yeniden dener. *NRetryReply* için 0 değeri bir anında yeniden deneme belirtir ve-1 çağrının iptalini belirtir.

İleti bekleyen gecikme süresi dolduğunda, kullanıcının iptal etmeyi veya çağrıyı yeniden denemesini seçebilmesi için OLE "meşgul iletişim kutusu" (bkz. [Copabusi iletişim](../../mfc/reference/colebusydialog-class.md)kutusu) görüntülenir. Bu iletişim kutusunu etkinleştirmek veya devre dışı bırakmak için [Enablebusi iletişim](#enablebusydialog) kutusunu çağırın.

Bir çağrı sırasında klavye veya fare iletisi beklendiğinde ve çağrı zaman aşımına uğradığından (ileti bekleyen gecikme aşıldığında), "yanıt vermiyor" iletişim kutusu görüntülenir. Bu iletişim kutusunu etkinleştirmek veya devre dışı bırakmak için [EnableNotRespondingDialog](#enablenotrespondingdialog) çağırın. Bu AFFAIRS 'nin genellikle bir şeyin yanlış geçmiş olduğunu ve kullanıcının sabırsız davranır aldığını belirtir.

İletişim kutuları devre dışı bırakıldığında, geçerli "yeniden dene yanıtı" her zaman meşgul uygulamalara yapılan çağrılar için kullanılır.

## <a name="see-also"></a>Ayrıca bkz.

[CCmdTarget sınıfı](../../mfc/reference/ccmdtarget-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CCmdTarget sınıfı](../../mfc/reference/ccmdtarget-class.md)
