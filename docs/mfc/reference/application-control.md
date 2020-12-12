---
description: 'Daha fazla bilgi edinin: uygulama denetimi'
title: Uygulama Denetimi
ms.date: 11/04/2016
helpviewer_keywords:
- application control [MFC]
ms.assetid: c1f69f15-e0fe-4515-9f36-d63d31869deb
ms.openlocfilehash: 20a777f5b7bb20870e9156ee090ff24ec4690f14
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97322830"
---
# <a name="application-control"></a>Uygulama Denetimi

OLE, uygulamalar ve nesneler üzerinde önemli denetim gerektirir. OLE sistem dll 'Leri uygulamaları otomatik olarak başlatıp serbest bırakabilir, bunların üretimini ve nesnelerin değiştirilmesini koordine edebilir. Bu konudaki işlevler bu gereksinimleri karşılar. OLE sistem dll 'Leri tarafından çağrılmalarının yanı sıra, bu işlevlerin bazen uygulamalar tarafından da çağrılması gerekir.

### <a name="application-control"></a>Uygulama Denetimi

| Ad | Açıklama |
|-|-|
|[AfxOleCanExitApp](#afxolecanexitapp)|Uygulamanın sonlandırılıp sonlandıramayacağını gösterir.|
|[AfxOleGetMessageFilter](#afxolegetmessagefilter)|Uygulamanın geçerli ileti filtresini alır.|
|[AfxOleGetUserCtrl](#afxolegetuserctrl)|Geçerli Kullanıcı denetimi bayrağını alır.|
|[AfxOleSetUserCtrl](#afxolesetuserctrl)|Kullanıcı denetimi bayrağını ayarlar veya temizler.|
|[AfxOleLockApp](#afxolelockapp)|Çerçevenin bir uygulamadaki etkin nesne sayısının genel sayısını artırır.|
|[AfxOleLockControl](#afxolelockcontrol)| Belirtilen denetimin sınıf fabrikasını kilitler. |
|[AfxOleUnlockApp](#afxoleunlockapp)|Bir uygulamadaki etkin nesne sayısı çerçevesinin sayısını azaltır.|
|[AfxOleUnlockControl](#afxoleunlockcontrol)| Belirtilen denetimin sınıf fabrikasının kilidini açar. |
|[AfxOleRegisterServerClass](#afxoleregisterserverclass)|OLE sistem kayıt defterine bir sunucu kaydeder.|
|[AfxOleSetEditMenu](#afxoleseteditmenu)|*TypeName* nesne komutu için Kullanıcı arabirimini uygular.|

## <a name="afxolecanexitapp"></a><a name="afxolecanexitapp"></a> AfxOleCanExitApp

Uygulamanın sonlandırılıp sonlandıramayacağını gösterir.

```
BOOL AFXAPI AfxOleCanExitApp();
```

### <a name="return-value"></a>Dönüş Değeri

Uygulamanın çıkış yapmak için sıfır dışında; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bir uygulama, nesnelerine yönelik bekleyen başvurular varsa sonlandırılmamalıdır. Genel işlevler, `AfxOleLockApp` `AfxOleUnlockApp` uygulama nesnelerine yapılan başvuruların bir sayacını sırasıyla artırır ve azaltır. Bu sayaç sıfır olmadığında uygulamanın sonlandırılması gerekir. Sayaç sıfır değilse, Kullanıcı sistem menüsünden Kapat ' ı seçtiğinde veya Dosya menüsünden çıkarken uygulamanın ana penceresi gizlenir (yok edilmez). Framework içinde bu işlevi çağırır `CFrameWnd::OnClose` .

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCAutomation#2](../../mfc/codesnippet/cpp/application-control_1.cpp)]

## <a name="requirements"></a>Gereksinimler

**Üstbilgi**: AfxDisp. h

## <a name="afxolegetmessagefilter"></a><a name="afxolegetmessagefilter"></a> AfxOleGetMessageFilter

Uygulamanın geçerli ileti filtresini alır.

```
COleMessageFilter* AFXAPI AfxOleGetMessageFilter();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli ileti filtresine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Geçerli `COleMessageFilter` `AfxGetApp` Uygulama nesnesine erişmek için çağırdığınız gibi, geçerli türetilmiş nesneye erişmek için bu işlevi çağırın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCAutomation#3](../../mfc/codesnippet/cpp/application-control_2.cpp)]

[!code-cpp[NVC_MFCAutomation#4](../../mfc/codesnippet/cpp/application-control_3.cpp)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi**: Afxwin. h

## <a name="afxolegetuserctrl"></a><a name="afxolegetuserctrl"></a> AfxOleGetUserCtrl

Geçerli Kullanıcı denetimi bayrağını alır.

```
BOOL AFXAPI AfxOleGetUserCtrl();
```

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı uygulamanın denetlikse sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Kullanıcı açıkça açıldığında veya yeni bir belge oluştururken uygulamanın denetimindeki kullanıcı denetimidir. Kullanıcı aynı zamanda uygulamanın OLE sistem dll 'Leri tarafından başlatılmadığından (başka bir deyişle, Kullanıcı uygulamayı sistem kabuğu ile başlatdıysa) denetim de olur.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi**: AfxDisp. h

## <a name="afxolesetuserctrl"></a><a name="afxolesetuserctrl"></a> AfxOleSetUserCtrl

İçin başvurusunda açıklanan Kullanıcı denetimi bayrağını ayarlar veya temizler `AfxOleGetUserCtrl` .

```cpp
void AFXAPI AfxOleSetUserCtrl(BOOL bUserCtrl);
```

### <a name="parameters"></a>Parametreler

*bUserCtrl*<br/>
Kullanıcı denetimi bayrağının ayarlanacağını veya temizlenip temizlenmeyeceğini belirtir.

### <a name="remarks"></a>Açıklamalar

Kullanıcı bir belge oluşturduğunda veya yüklediğinde bu işlevi çağırır, ancak bir belge yüklendiğinde veya bir kapsayıcı uygulamasından katıştırılmış bir nesne yükleme gibi dolaylı bir eylem aracılığıyla oluşturulduğunda değil.

Uygulamanızdaki başka eylemler uygulamayı uygulamanın denetimine yerleştirmelidir bu işlevi çağırın.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi**: AfxDisp. h

## <a name="afxolelockapp"></a><a name="afxolelockapp"></a> AfxOleLockApp

Çerçevenin uygulamadaki etkin nesne sayısının genel sayısını artırır.

```cpp
void AFXAPI AfxOleLockApp();
```

### <a name="remarks"></a>Açıklamalar

Çerçeve, bir uygulamada etkin olan nesne sayısının sayısını tutar. `AfxOleLockApp`Ve `AfxOleUnlockApp` işlevleri sırasıyla bu sayıyı artırır ve azaltır.

Kullanıcı, etkin nesneleri olan bir uygulamayı kapatmayı denediğinde — etkin nesne sayısı sıfır olmayan bir uygulama — çerçeve, uygulamayı tamamen kapatmak yerine kullanıcının görünümünden gizler. `AfxOleCanExitApp`İşlevi uygulamanın sonlandırılıp sonlanamayacağını gösterir.

`AfxOleLockApp`OLE arabirimleri sunan herhangi bir nesneden, bu nesnenin bir istemci uygulaması tarafından hala kullanılmaya devam edilmesi istenmeyen bir biçimde olması isteniyorsa, çağırın. Ayrıca, `AfxOleUnlockApp` oluşturucuda çağıran herhangi bir nesnenin `AfxOleLockApp` yıkıcısında çağırın. Varsayılan olarak, `COleDocument` (ve türetilmiş sınıflar) uygulamayı otomatik olarak kilitler ve kilidi açar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCAutomation#5](../../mfc/codesnippet/cpp/application-control_4.cpp)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi**: AfxDisp. h

## <a name="afxoleunlockapp"></a><a name="afxoleunlockapp"></a> AfxOleUnlockApp

Çerçevenin uygulamadaki etkin nesne sayısını azaltır.

```cpp
void AFXAPI AfxOleUnlockApp();
```

### <a name="remarks"></a>Açıklamalar

`AfxOleLockApp`Daha fazla bilgi için bkz..

Etkin nesne sayısı sıfıra ulaştığında, `AfxOleOnReleaseAllObjects` çağrılır.

### <a name="example"></a>Örnek

[AfxOleLockApp](#afxolelockapp)için örneğe bakın.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi**: AfxDisp. h

## <a name="afxolelockcontrol"></a>AfxOleLockControl

Denetimle ilişkili dinamik olarak oluşturulan verilerin bellekte kalması için, belirtilen denetimin sınıf fabrikasını kilitler.

### <a name="syntax"></a>Sözdizimi

```
BOOL AFXAPI AfxOleLockControl(  REFCLSID clsid  );
BOOL AFXAPI AfxOleLockControl( LPCTSTR lpszProgID );
```

### <a name="parameters"></a>Parametreler

*in*<br/>
Denetimin benzersiz sınıf KIMLIĞI.

*lpszProgID*<br/>
Denetimin benzersiz program KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Denetimin sınıf fabrikası başarıyla kilitliyse sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu, denetimlerin görüntülenmesini önemli ölçüde hızlandırabilir. Örneğin, iletişim kutusunda bir denetim oluşturup ile denetimi kilitledikten sonra `AfxOleLockControl` , iletişim kutusu her gösterildiğinde veya yok edildiğinde yeniden oluşturmanız ve sonlandırmanıza gerek yoktur. Kullanıcı bir iletişim kutusunu açar ve kapatır, denetimlerinizi kilitlemek performansı önemli ölçüde artırabilir. Denetimi yok etmeye hazırsanız çağırın `AfxOleUnlockControl` .

### <a name="example"></a>Örnek

```cpp
// Starts and locks control's (Microsoft Calendar) class factory.
// Control will remain in memory for lifetime of
// application or until AfxOleUnlockControl() is called.

AfxOleLockControl(_T("MSCAL.Calendar"));
```

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxwin. h

## <a name="afxoleregisterserverclass"></a><a name="afxoleregisterserverclass"></a> AfxOleRegisterServerClass

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

*in*<br/>
Sunucunun OLE sınıf KIMLIĞINE başvuru.

*lpszClassName*<br/>
Sunucu nesnelerinin sınıf adını içeren bir dize işaretçisi.

*lpszShortTypeName*<br/>
Sunucunun nesne türünün (örneğin, "grafik") kısa adını içeren bir dize işaretçisi.

*lpszLongTypeName*<br/>
Sunucunun nesne türünün uzun adını içeren bir dize işaretçisi, örneğin "Microsoft Excel 5,0 Chart."

*nAppType*<br/>
OLE uygulamasının türünü belirten OLE_APPTYPE numaralandırmasından alınan bir değer. Olası değerler şunlardır:

- OAT_INPLACE_SERVER sunucusu, tam sunucu Kullanıcı arabirimine sahiptir.

- OAT_SERVER sunucusu yalnızca katıştırmayı destekler.

- OAT_CONTAINER kapsayıcı, eklenebilir bağlantıları destekler.

- OAT_DISPATCH_OBJECT `IDispatch` özellikli nesne.

*rglpszRegister*<br/>
Anahtarlar için mevcut bir değer bulunamazsa OLE sistem kayıt defterine eklenecek anahtarları ve değerleri temsil eden dizelerin işaretçisi dizisi.

*rglpszOverwrite*<br/>
Kayıt defteri verilen anahtarlar için mevcut değerler içeriyorsa OLE sistem kayıt defterine eklenecek anahtarları ve değerleri temsil eden dizelerin işaretçisi dizisi.

### <a name="return-value"></a>Dönüş Değeri

Sunucu sınıfı başarıyla kaydedilmişse sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Çoğu uygulama `COleTemplateServer::Register` , uygulamanın belge türlerini kaydetmek için kullanılabilir. Uygulamanızın sistem kayıt defteri biçimi tipik modele uymuyorsa, `AfxOleRegisterServerClass` daha fazla denetim için kullanabilirsiniz.

Kayıt defteri bir anahtarlar ve değerler kümesinden oluşur. *RglpszRegister* ve *rglpszOverwrite* bağımsız değişkenleri, her biri bir anahtar ve bir **null** karakterle () ayrılmış bir değer içeren dizeler için işaretçilerin dizeleridir `'\0'` . Bu dizelerin her biri, yerleri% *1* karakter dizileri tarafından işaretlenmiş ve *%5* ile değişen değiştirilebilir parametrelere sahip olabilir.

Semboller aşağıdaki gibi doldurulur:

|Sembol|Değer|
|------------|-----------|
|%1|Sınıf KIMLIĞI, dize olarak biçimlendirildi|
|%2|Sınıf adı|
|%3|Yürütülebilir dosyanın yolu|
|%4|Kısa tür adı|
|%5|Uzun tür adı|

### <a name="requirements"></a>Gereksinimler

**Üstbilgi**: AfxDisp. h

## <a name="afxoleseteditmenu"></a><a name="afxoleseteditmenu"></a> AfxOleSetEditMenu

*TypeName* nesne komutu için Kullanıcı arabirimini uygular.

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

*pClient*<br/>
İstemci OLE öğesine yönelik bir işaretçi.

*pMenu*<br/>
Güncelleştirileceği menü nesnesine yönelik bir işaretçi.

*Imtri öğesi*<br/>
Güncelleştirileceği menü öğesinin dizini.

*nIDVerbMin*<br/>
Birincil fiilye karşılık gelen komut KIMLIĞI.

*Nıdverbmax*<br/>
Son fiilye karşılık gelen komut KIMLIĞI.

*Nıdconvert*<br/>
Dönüştür menü öğesinin KIMLIĞI.

### <a name="remarks"></a>Açıklamalar

Sunucu yalnızca birincil bir fiili değer tanırsa, menü öğesi "fiil *TypeName* nesnesi" olur ve Kullanıcı komutu seçtiğinde *nIDVerbMin* komutu gönderilir. Sunucu birkaç fiil algılarsa, menü öğesi " *TypeName* nesnesi" olur ve Kullanıcı komutu seçtiğinde tüm fiillerin listelendiği bir alt menü görünür. Kullanıcı alt menüden bir fiil seçtiğinde, ilk fiil seçilirse *nIDVerbMin* gönderilir, ikinci fiil seçilirse *nIDVerbMin* + 1 gönderilir ve bu şekilde devam eder. Varsayılan `COleDocument` uygulama bu özelliği otomatik olarak işler.

İstemcinizin uygulama kaynak betiğinizde (. RC) dosyası:

**#include \<afxolecl.rc>**

### <a name="requirements"></a>Gereksinimler

**Üstbilgi**: afxole. h

## <a name="afxoleunlockcontrol"></a><a name="afxoleunlockcontrol"></a> AfxOleUnlockControl

Belirtilen denetimin sınıf fabrikasının kilidini açar.

### <a name="syntax"></a>Sözdizimi

```
BOOL AFXAPI AfxOleUnlockControl( REFCLSID clsid );
BOOL AFXAPI AfxOleUnlockControl( LPCTSTR lpszProgID );
```

### <a name="parameters"></a>Parametreler

*in*<br/>
Denetimin benzersiz sınıf KIMLIĞI.

*lpszProgID*<br/>
Denetimin benzersiz program KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Denetimin sınıf fabrikası başarıyla kilitse sıfır dışında; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Denetim ile birlikte kilitlenir `AfxOleLockControl` , böylece denetimle ilişkili dinamik olarak oluşturulan veriler bellekte kalır. Bu, denetimin görüntülenmesi önemli ölçüde hızlanır, çünkü her görüntülendiğinde denetim oluşturulmamalıdır ve yok edilir. Denetimi yok etmeye hazırsanız çağırın `AfxOleUnlockControl` .

### <a name="example"></a>Örnek

```cpp
// Unlock control's (Microsoft Calendar Control) class factory.

AfxOleUnlockControl(_T("MSCAL.Calendar"));
```

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxwin. h

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve genel öğeler](mfc-macros-and-globals.md)<br/>
