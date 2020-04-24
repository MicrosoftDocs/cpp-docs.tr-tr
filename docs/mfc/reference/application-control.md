---
title: Uygulama Denetimi
ms.date: 11/04/2016
helpviewer_keywords:
- application control [MFC]
ms.assetid: c1f69f15-e0fe-4515-9f36-d63d31869deb
ms.openlocfilehash: 7e18b4504ddbfdd9a4399f33c34c6e6e9900233b
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752864"
---
# <a name="application-control"></a>Uygulama Denetimi

OLE, uygulamalar ve nesneleri üzerinde önemli ölçüde kontrol gerektirir. OLE sistemi DL'leri uygulamaları otomatik olarak başlatabilmeli ve serbest bırakabilmeli, nesnelerin üretimini ve modifikasyonlarını koordine edebilmelidir. Bu konudaki işlevler bu gereksinimleri karşılar. OLE sistemi DLs tarafından çağrılması ek olarak, bu işlevleri bazen de uygulamalar tarafından çağrılmalıdır.

### <a name="application-control"></a>Uygulama Denetimi

|||
|-|-|
|[AfxOleCanExitApp](#afxolecanexitapp)|Uygulamanın sonlandırılıp sonlandırılamayacağını gösterir.|
|[AfxOleGetMessageFiltre](#afxolegetmessagefilter)|Uygulamanın geçerli ileti filtresini alır.|
|[AfxOleGetUserCtrl](#afxolegetuserctrl)|Geçerli kullanıcı denetimi bayrağını alır.|
|[AfxOleSetUserCtrl](#afxolesetuserctrl)|Kullanıcı denetimi bayrağını ayarlar veya temizler.|
|[Afxolelockapp](#afxolelockapp)|Bir uygulamadaki etkin nesne sayısının çerçevesinin genel sayısını artımları.|
|[AfxOleLockControl](#afxolelockcontrol)| Belirtilen denetimin sınıf fabrikasını kilitler. |
|[AfxOleUnlockApp](#afxoleunlockapp)|Bir uygulamadaki etkin nesne sayısının çerçeve sayısını eriter.|
|[AfxOleUnlockControl](#afxoleunlockcontrol)| Belirtilen denetimin sınıf fabrikasının kilidini açar. |
|[AfxOleRegisterServerClass](#afxoleregisterserverclass)|OLE sistem kayıt defterine bir sunucu kaydeder.|
|[AfxOleSetEditMenü](#afxoleseteditmenu)|*Ad* Nesne komutu için kullanıcı arabirimini uygular.|

## <a name="afxolecanexitapp"></a><a name="afxolecanexitapp"></a>AfxOleCanExitApp

Uygulamanın sonlandırılıp sonlandırılamayacağını gösterir.

```
BOOL AFXAPI AfxOleCanExitApp();
```

### <a name="return-value"></a>Dönüş Değeri

Uygulama çıkabiliyorsa sıfır olmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Nesnelerine olağanüstü başvurular varsa, uygulama sonlandırmamalıdır. Genel `AfxOleLockApp` işlevler `AfxOleUnlockApp` ve artış ve decrement, sırasıyla, uygulamanın nesnelerine başvuru sayacı. Bu sayaç sıfır olmadığında uygulama sonlandırmamalıdır. Sayaç sıfır değilse, kullanıcı sistem menüsünden Kapat'ı veya Dosya menüsünden Çık'ı seçtiğinde uygulamanın ana penceresi gizlenir (yok edilmez). Çerçeve bu işlevi `CFrameWnd::OnClose`.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCAutomation#2](../../mfc/codesnippet/cpp/application-control_1.cpp)]

## <a name="requirements"></a>Gereksinimler

**Üstbilgi**: afxdisp.h

## <a name="afxolegetmessagefilter"></a><a name="afxolegetmessagefilter"></a>AfxOleGetMessageFiltre

Uygulamanın geçerli ileti filtresini alır.

```
COleMessageFilter* AFXAPI AfxOleGetMessageFilter();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli ileti filtresi için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Geçerli uygulama nesnesine `COleMessageFilter`erişmek için çağıracağınız gibi, geçerli türetilmiş nesneye erişmek için bu işlevi arayın. `AfxGetApp`

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCAutomation#3](../../mfc/codesnippet/cpp/application-control_2.cpp)]

[!code-cpp[NVC_MFCAutomation#4](../../mfc/codesnippet/cpp/application-control_3.cpp)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi**: afxwin.h

## <a name="afxolegetuserctrl"></a><a name="afxolegetuserctrl"></a>AfxOleGetUserCtrl

Geçerli kullanıcı denetimi bayrağını alır.

```
BOOL AFXAPI AfxOleGetUserCtrl();
```

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı uygulamanın denetimindeyse sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Kullanıcı açıkça yeni bir belge açtığında veya oluşturduğunda, kullanıcı uygulamanın denetimindedir. Uygulama OLE sistemi DLLs tarafından başlatılmadıysa, kullanıcı da kontrol altındadır — başka bir deyişle, kullanıcı uygulamayı sistem kabuğuyla başlattıysa.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi**: afxdisp.h

## <a name="afxolesetuserctrl"></a><a name="afxolesetuserctrl"></a>AfxOleSetUserCtrl

'nin başvurusunda açıklanan kullanıcı denetimi bayrağını ayarlar veya `AfxOleGetUserCtrl`temizler.

```cpp
void AFXAPI AfxOleSetUserCtrl(BOOL bUserCtrl);
```

### <a name="parameters"></a>Parametreler

*bUserCtrl*<br/>
Kullanıcı denetimi bayrağının ayarlanıp ayarlanmayacağını veya temizlenip temizlenmeyeceğini belirtir.

### <a name="remarks"></a>Açıklamalar

Çerçeve, kullanıcı bir belge oluşturduğunda veya yüklendiğinde, ancak bir belge yüklendiğinde veya kapsayıcı uygulamasından katıştırılmış bir nesne nin yüklenmesi gibi dolaylı bir eylem le oluşturulduğunda bu işlevi çağırır.

Uygulamanızdaki diğer eylemler kullanıcıyı uygulamanın denetimine sokacaksa bu işlevi arayın.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi**: afxdisp.h

## <a name="afxolelockapp"></a><a name="afxolelockapp"></a>Afxolelockapp

Çerçevenin uygulamadaki etkin nesne sayısının genel sayısını artımları.

```cpp
void AFXAPI AfxOleLockApp();
```

### <a name="remarks"></a>Açıklamalar

Çerçeve, bir uygulamada etkin nesne sayısının sayısını tutar. Ve `AfxOleLockApp` `AfxOleUnlockApp` işlevleri, sırasıyla, artış ve bu sayı kararname.

Kullanıcı etkin nesnelere sahip bir uygulamayı kapatmaya çalıştığında -etkin nesnelerin sayısının sıfır olmadığı bir uygulama- çerçeve uygulamayı tamamen kapatmak yerine kullanıcının görünümünden gizler. İşlev, `AfxOleCanExitApp` uygulamanın sonlandırılıp sonlandırılamayacağını gösterir.

İstemci uygulaması tarafından hala kullanılırken bu nesnenin yok edilmesi istenmeyen bir nesne yse, OLE arabirimlerini ortaya çıkaran herhangi bir nesneden çağrı. `AfxOleLockApp` Ayrıca, `AfxOleUnlockApp` oluşturucuyu çağıran `AfxOleLockApp` herhangi bir nesnenin yıkıcısını çağırın. Varsayılan olarak, `COleDocument` (ve türetilen sınıflar) otomatik olarak kilitleyin ve uygulama kilidini.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCAutomation#5](../../mfc/codesnippet/cpp/application-control_4.cpp)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi**: afxdisp.h

## <a name="afxoleunlockapp"></a><a name="afxoleunlockapp"></a>AfxOleUnlockApp

Çerçevenin uygulamadaki etkin nesnelerin sayısını eriter.

```cpp
void AFXAPI AfxOleUnlockApp();
```

### <a name="remarks"></a>Açıklamalar

Daha `AfxOleLockApp` fazla bilgi için bkz.

Etkin nesnelerin sayısı sıfıra ulaştığında, `AfxOleOnReleaseAllObjects` denir.

### <a name="example"></a>Örnek

[AfxOleLockApp örneğine](#afxolelockapp)bakın.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi**: afxdisp.h

## <a name="afxolelockcontrol"></a>AfxOleLockControl

Denetimle ilişkili dinamik olarak oluşturulan verilerin bellekte kalması için belirtilen denetimin sınıf fabrikasını kilitler.

### <a name="syntax"></a>Sözdizimi

```
BOOL AFXAPI AfxOleLockControl(  REFCLSID clsid  );
BOOL AFXAPI AfxOleLockControl( LPCTSTR lpszProgID );
```

### <a name="parameters"></a>Parametreler

*Clsıd*<br/>
Denetimin benzersiz sınıf kimliği.

*lpszProgID*<br/>
Denetimin benzersiz program kimliği.

### <a name="return-value"></a>Dönüş Değeri

Denetimin sınıf fabrikası başarıyla kilitlenmişse sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu, denetimlerin görüntülenmesini önemli ölçüde hızlandırabilir. Örneğin, bir iletişim kutusunda bir denetim oluşturduğunuzda ve `AfxOleLockControl`denetimi kilitledikten sonra, iletişim her gösterildiğinde veya yok edildiğinde yeniden oluşturmanız ve öldürmeniz gerekmez. Kullanıcı bir iletişim kutusunu tekrar tekrar açıp kapatırsa, denetimlerinizi kilitlemek performansı önemli ölçüde artırabilir. Kontrolü yok etmeye hazır olduğunuzda, `AfxOleUnlockControl`.

### <a name="example"></a>Örnek

```cpp
// Starts and locks control's (Microsoft Calendar) class factory.
// Control will remain in memory for lifetime of
// application or until AfxOleUnlockControl() is called.

AfxOleLockControl(_T("MSCAL.Calendar"));
```

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwin.h

## <a name="afxoleregisterserverclass"></a><a name="afxoleregisterserverclass"></a>AfxOleRegisterServerClass

Bu işlev, sunucunuzu OLE sistem kayıt defterine kaydetmenizi sağlar.

```
BOOL AFXAPI AfxOleRegisterServerClass(
    REFCLSID clsid,
    LPCTSTR lpszClassName,
    LPCTSTR lpszShortTypeName,
    LPCTSTR lpszLongTypeName,
    OLE_APPTYPE nAppType = OAT_SERVER,
    LPCTSTR* rglpszRegister = NULL,
    LPCTSTR* rglpszOverwrite = NULL);
```

### <a name="parameters"></a>Parametreler

*Clsıd*<br/>
Sunucunun OLE sınıfı kimliğine başvuru.

*lpszClassName*<br/>
Sunucunun nesnelerinin sınıf adını içeren bir dize işaretçi.

*lpszShortTypeName*<br/>
Sunucunun nesne türünün kısa adını içeren "Grafik" gibi bir dize işaretçisi.

*lpszLongTypeName*<br/>
Sunucunun nesne türünün uzun adını içeren "Microsoft Excel 5.0 Chart" gibi bir dize işaretçisi.

*nAppType*<br/>
OLE uygulamasının türünü belirten, numaralandırma OLE_APPTYPE alınan bir değer. Olası değerler şunlardır:

- OAT_INPLACE_SERVER Server tam sunucu kullanıcı arayüzüne sahiptir.

- OAT_SERVER Sunucu yalnızca katıştırma desteklemektedir.

- OAT_CONTAINER Konteyner katıştırma bağlantıları destekler.

- OAT_DISPATCH_OBJECT `IDispatch`yetenekli nesne.

*rglpszKayıt*<br/>
Anahtarlar için varolan değerler bulunamazsa, OLE sistem kayıt defterine eklenecek anahtarları ve değerleri temsil eden dizelere işaretçiler dizisi.

*rglpszOverwrite*<br/>
Kayıt defteri, verilen anahtarlar için varolan değerleri içeriyorsa, OLE sistem kayıt defterine eklenecek anahtarları ve değerleri temsil eden dizeler dizi.

### <a name="return-value"></a>Dönüş Değeri

Sunucu sınıfı başarıyla kaydedilmişse sıfıra inme; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Çoğu uygulama, `COleTemplateServer::Register` uygulamanın belge türlerini kaydetmek için kullanabilir. Uygulamanızın sistem kayıt defteri biçimi tipik desene uymuyorsa, `AfxOleRegisterServerClass` daha fazla denetim için kullanabilirsiniz.

Kayıt defteri bir anahtar lar ve değerler kümesinden oluşur. *rglpszRegister* ve *rglpszOverwrite* bağımsız değişkenleri, her biri bir anahtar ve **NULL** karakteriyle ayrılmış bir `'\0'`değerden oluşan dizelere işaretçiler dizileridir ( ). Bu dizelerin her biri, yerleri *%1* ile *%5*arasında karakter dizileri ile işaretlenmiş değiştirilebilir parametrelere sahip olabilir.

Semboller aşağıdaki gibi doldurulur:

|Sembol|Değer|
|------------|-----------|
|%1|Sınıf kimliği, dize olarak biçimlendirilmiş|
|%2|Sınıf adı|
|%3|Yürütülebilir dosyaya giden yol|
|%4|Kısa tür adı|
|%5|Uzun tür adı|

### <a name="requirements"></a>Gereksinimler

**Üstbilgi**: afxdisp.h

## <a name="afxoleseteditmenu"></a><a name="afxoleseteditmenu"></a>AfxOleSetEditMenü

*Ad* Nesne komutu için kullanıcı arabirimini uygular.

```cpp
void AFXAPI AfxOleSetEditMenu(
    COleClientItem* pClient,
    CMenu* pMenu,
    UINT iMenuItem,
    UINT nIDVerbMin,
    UINT nIDVerbMax = 0,
    UINT nIDConvert = 0);
```

### <a name="parameters"></a>Parametreler

*pİsteSİ*<br/>
İstemci OLE öğesiiçin bir işaretçi.

*pMenü*<br/>
Güncellenecek menü nesnesine işaretçi.

*iMenuItem*<br/>
Güncellenecek menü öğesinin dizini.

*nIDVerbMin*<br/>
Birincil fiille karşılık gelen komut kimliği.

*nIDVerbMax*<br/>
Son fiille karşılık gelen komut kimliği.

*nIDConvert*<br/>
Dönüştür menüsü öğesi için kimlik.

### <a name="remarks"></a>Açıklamalar

Sunucu yalnızca birincil bir fiil tanıyorsa, menü öğesi "fiil *türü adı* Nesne" olur ve kullanıcı komutu seçtiğinde *nIDVerbMin* komutu gönderilir. Sunucu birkaç fiil tanıyorsa, menü öğesi *"ad* nesnesi" olur ve kullanıcı komutu seçtiğinde tüm fiilleri listeleyen bir alt menü görüntülenir. Kullanıcı alt menüden bir fiil seçtiğinde, ilk fiil seçilirse *nIDVerbMin* , ikinci fiil seçilirse *nIDVerbMin* + 1 gönderilir. Varsayılan `COleDocument` uygulama bu özelliği otomatik olarak işler.

İstemcinizin uygulama kaynak komut dosyasında aşağıdaki ifadeye sahip olmalısınız (. RC) dosyası:

**#include \<afxolecl.rc>**

### <a name="requirements"></a>Gereksinimler

**Üstbilgi**: afxole.h

## <a name="afxoleunlockcontrol"></a><a name="afxoleunlockcontrol"></a>AfxOleUnlockControl

Belirtilen denetimin sınıf fabrikasının kilidini açar.

### <a name="syntax"></a>Sözdizimi

```
BOOL AFXAPI AfxOleUnlockControl( REFCLSID clsid );
BOOL AFXAPI AfxOleUnlockControl( LPCTSTR lpszProgID );
```

### <a name="parameters"></a>Parametreler

*Clsıd*<br/>
Denetimin benzersiz sınıf kimliği.

*lpszProgID*<br/>
Denetimin benzersiz program kimliği.

### <a name="return-value"></a>Dönüş Değeri

Denetimin sınıf fabrikası başarıyla kilidi açıldıysa sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Denetim, denetimle `AfxOleLockControl`ilişkili dinamik olarak oluşturulan verilerin bellekte kalması için kilitlenir. Denetim her görüntülendiğinde oluşturulmaması ve yok edilmesi gerekmedığından, bu denetimin görüntülenmesini önemli ölçüde hızlandırabilir. Kontrolü yok etmeye hazır olduğunuzda, `AfxOleUnlockControl`.

### <a name="example"></a>Örnek

```cpp
// Unlock control's (Microsoft Calendar Control) class factory.

AfxOleUnlockControl(_T("MSCAL.Calendar"));
```

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwin.h

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve Küreseller](mfc-macros-and-globals.md)<br/>
