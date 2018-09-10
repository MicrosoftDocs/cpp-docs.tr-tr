---
title: Uygulama denetimi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros
dev_langs:
- C++
helpviewer_keywords:
- application control [MFC]
ms.assetid: c1f69f15-e0fe-4515-9f36-d63d31869deb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 538a376dd14eae32864b494b7e79db1c89686b84
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44315021"
---
# <a name="application-control"></a>Uygulama Denetimi
OLE uygulamaları ve bunların nesneler üzerinde önemli denetim gerektirir. OLE sistem DLL'lerini Başlat ve uygulamaları otomatik olarak yayınlayın, üretim ve değişikliği nesnelerin koordine etmek ve benzeri olması gerekir. Bu konudaki işlevleri bu gereksinimleri karşılar. OLE sistem DLL'lerini çağrılan ek olarak, bu işlevler, bazen de uygulamalar tarafından çağrılmalıdır. 
  
### <a name="application-control"></a>Uygulama Denetimi  
  
|||  
|-|-|  
|[AfxOleCanExitApp](#afxolecanexitapp)|Uygulamayı sonlandırabilirsiniz olup olmadığını gösterir.|  
|[AfxOleGetMessageFilter](#afxolegetmessagefilter)|Uygulamanın geçerli ileti filtresini alır.|  
|[AfxOleGetUserCtrl](#afxolegetuserctrl)|Geçerli kullanıcı denetimi bayrağı alır.|  
|[AfxOleSetUserCtrl](#afxolesetuserctrl)|Kullanıcı denetimi bayrağını kaldırır veya ayarlar.|  
|[AfxOleLockApp](#afxolelockapp)|Framework'ün genel bir uygulamada etkin nesne sayısını sayısını artırır.|  
|[AfxOleLockControl](#afxolelockcontrol)| Sınıf üretecini belirtilen denetiminin kilitler. |
|[AfxOleUnlockApp](#afxoleunlockapp)|Azaltır uygulamada etkin nesne sayısını framework'ün sayısı.| 
|[AfxOleUnlockControl](#afxoleunlockcontrol)| Sınıf üretecini belirtilen denetiminin kilidini açar. |
|[AfxOleRegisterServerClass](#afxoleregisterserverclass)|Bir sunucuya OLE sistem kayıt defterine kaydeder.|  
|[AfxOleSetEditMenu](#afxoleseteditmenu)|Kullanıcı arabirimi uygulayan *typename* nesne komutu.|  

  
##  <a name="afxolecanexitapp"></a>  AfxOleCanExitApp  
 Uygulamayı sonlandırabilirsiniz olup olmadığını gösterir.  
  
```   
BOOL AFXAPI AfxOleCanExitApp(); 
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Uygulamadan çıkmak olursa sıfır dışı; Aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bekleyen nesnelerine başvurular varsa uygulamanın sonlanmalıdır değil. Genel işlevler `AfxOleLockApp` ve `AfxOleUnlockApp` artırın ve sırasıyla bir sayacı uygulamanın nesnelere yapılan başvuruların azaltma. Bu sayaç, sıfır dışında olduğunda uygulama sonlanmalıdır değil. Sayaç sıfır değilse, uygulamanın ana pencere kullanıcı sistem menüsünden veya çıkış Dosya menüsünden Kapat seçtiğinde (değil yok) gizlidir. Bu işlev çağrıları framework `CFrameWnd::OnClose`.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCAutomation#2](../../mfc/codesnippet/cpp/application-control_1.cpp)]  

## <a name="requirements"></a>Gereksinimler  
 **Üst bilgi**: afxdisp.h 

##  <a name="afxolegetmessagefilter"></a>  AfxOleGetMessageFilter  
 Uygulamanın geçerli ileti filtresini alır.  
  
```   
COleMessageFilter* AFXAPI AfxOleGetMessageFilter(); 
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli İleti Filtresi için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Geçerli erişmek için bu işlevi çağırın `COleMessageFilter`-yalnızca çağıracak şekilde nesne, türetilmiş `AfxGetApp` geçerli uygulama nesnesinin erişmek için.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCAutomation#3](../../mfc/codesnippet/cpp/application-control_2.cpp)]  
  
 [!code-cpp[NVC_MFCAutomation#4](../../mfc/codesnippet/cpp/application-control_3.cpp)]  

### <a name="requirements"></a>Gereksinimler  
 **Üst bilgi**: afxwin.h 

##  <a name="afxolegetuserctrl"></a>  AfxOleGetUserCtrl  
 Geçerli kullanıcı denetimi bayrağı alır.  
  
```   
BOOL AFXAPI AfxOleGetUserCtrl(); 
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kullanıcı uygulama denetiminde ise sıfır olmayan; Aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanıcı açıkça açık veya yeni bir belge oluşturulan kullanıcı uygulama denetiminde olur. Uygulama OLE sistem DLL'lerini değil başlatıldıysa kullanıcı denetiminde olsa — diğer bir deyişle, kullanıcının uygulama system kabuğu ile başlatılan durumunda.  

### <a name="requirements"></a>Gereksinimler  
 **Üst bilgi**: afxdisp.h

##  <a name="afxolesetuserctrl"></a>  AfxOleSetUserCtrl  
 Başvuru için açıklanan kullanıcı denetimi bayrağını ayarlar veya temizler `AfxOleGetUserCtrl`.  
  
```  
void AFXAPI AfxOleSetUserCtrl(BOOL bUserCtrl); 
```  
  
### <a name="parameters"></a>Parametreler  
 *bUserCtrl*  
 Kullanıcı denetimi bayrağı ayarlayın ya da seçili olup olmadığını belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir belge yüklendiğinde veya bir kapsayıcı uygulamasından katıştırılmış nesne yükleme gibi dolaylı bir eylem aracılığıyla oluşturulan değil, framework kullanıcı oluşturduğunda veya bir belgeyi yükler, ancak bu işlevi çağırır.  
  
 Diğer Eylemler uygulamanızdaki kullanıcı uygulama denetiminde koymanız gerekir, bu işlevi çağırın.  

### <a name="requirements"></a>Gereksinimler  
 **Üst bilgi**: afxdisp.h

##  <a name="afxolelockapp"></a>  AfxOleLockApp  
 Framework'ün genel sayısını uygulamadaki etkin nesne sayısını artırır.  
  
```   
void AFXAPI AfxOleLockApp(); 
```  
  
### <a name="remarks"></a>Açıklamalar  
 Framework nesneleri sayısını uygulamada etkin tutar. `AfxOleLockApp` Ve `AfxOleUnlockApp` işlevleri sırasıyla artırmak ve bu sayı azaltma.  
  
 Kullanıcı çalıştığında, etkin nesneleri olan bir uygulamayı kapatmak — etkin nesnelerin sayımını olduğu sıfır olmayan bir uygulama — framework tamamen kapatmak yerine kullanıcının görünümünden uygulamayı gizler. `AfxOleCanExitApp` İşlevi, uygulamayı sonlandırabilirsiniz olup olmadığını gösterir.  
  
 Çağrı `AfxOleLockApp` istenmeyen o nesnenin bir istemci uygulaması tarafından halen kullanılmakta sırasında yok edileceği için, OLE arabirimleri kullanıma açıp herhangi bir nesneden. Ayrıca `AfxOleUnlockApp` çağıran herhangi bir nesnenin bir yok edici içinde `AfxOleLockApp` oluşturucuda. Varsayılan olarak, `COleDocument` (ve türetilmiş sınıflar) otomatik olarak Kilitle ve uygulama kilidini açın.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCAutomation#5](../../mfc/codesnippet/cpp/application-control_4.cpp)]  

### <a name="requirements"></a>Gereksinimler  
 **Üst bilgi**: afxdisp.h

##  <a name="afxoleunlockapp"></a>  AfxOleUnlockApp  
 Azaltır framework'ün uygulamadaki etkin nesne sayısı.  
  
```   
void AFXAPI AfxOleUnlockApp(); 
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: `AfxOleLockApp` daha fazla bilgi için.  
  
 Etkin nesne sayısı sıfır ulaştığında `AfxOleOnReleaseAllObjects` çağrılır.  
  
### <a name="example"></a>Örnek  
 Örneğin bakın [AfxOleLockApp](#afxolelockapp).  

### <a name="requirements"></a>Gereksinimler  
 **Üst bilgi**: afxdisp.h  

 ## <a name="afxolelockcontrol"></a>AfxOleLockControl
Sınıf üretecini belirtilen denetiminin, denetimle ilişkili dinamik olarak oluşturulan veri bellekte kalır. böylece kilitler.  
   
### <a name="syntax"></a>Sözdizimi    
```
BOOL AFXAPI AfxOleLockControl(  REFCLSID clsid  );  
BOOL AFXAPI AfxOleLockControl( LPCTSTR lpszProgID );  
```
### <a name="parameters"></a>Parametreler  
 *CLSID*  
 Denetim sınıfı benzersiz kimliği.  
  
 *lpszProgID*  
 Denetim programı benzersiz kimliği.  
   
### <a name="return-value"></a>Dönüş Değeri  
 Denetimin sınıf üreteci başarıyla kilitliydi olursa sıfır dışı; Aksi durumda 0.  
   
### <a name="remarks"></a>Açıklamalar  
 Bu, önemli ölçüde denetimlerin görünümünü hızlandırabilir. Örneğin, bir kez, iletişim kutusunda bir denetimi oluşturma ve Denetim ile kilitleme `AfxOleLockControl`, oluşturma ve iletişim kutusunda gösterilen veya yok olması her zaman yeniden KILL gerekmez. Kullanıcı açılır ve sürekli bir iletişim kutusu kapanır, denetimleri kilitleme performansı önemli ölçüde artırabilir. Kontrol edilecek hazır olduğunuzda, çağrı `AfxOleUnlockControl`.  
   
### <a name="example"></a>Örnek  
```cpp
// Starts and locks control's (Microsoft Calendar) class factory. 
// Control will remain in memory for lifetime of
// application or until AfxOleUnlockControl() is called.

AfxOleLockControl(_T("MSCAL.Calendar"));
```
   
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwin.h  
   
### <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları ve genel öğeleri](mfc-macros-and-globals.md)   
 [AfxOleUnlockControl](#afxoleunlockcontrol)
 
##  <a name="afxoleregisterserverclass"></a>  AfxOleRegisterServerClass  
 Bu işlev, sunucunuzun OLE sistem kayıt defterinde kaydetmenize olanak sağlar.  
  
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
 *CLSID*  
 Sunucunun OLE sınıf kimliği başvurusu  
  
 *lpszClassName*  
 Sunucu nesneleri sınıf adını içeren bir dize işaretçisi.  
  
 *lpszShortTypeName*  
 Sunucu nesne türü "Grafiği" gibi kısa adını içeren bir dize işaretçisi  
  
 *lpszLongTypeName*  
 "Microsoft Excel 5.0 grafiği" gibi sunucunun nesne türü uzun adını içeren bir dize işaretçisi  
  
 *nAppType*  
 OLE uygulama türünü belirleme OLE_APPTYPE numaralandırma alınan bir değer. Olası değerler şunlardır:  
  
- Oat_ınplace_server sunucunuzun tam sunucu kullanıcı arabirimi var.  
  
- OAT_SERVER sunucusu yalnızca ekleme destekler.  
  
- Oat_contaıner kapsayıcı katıştırma için destekler.  
  
- Oat_dıspatch_object `IDispatch`-yeteneğine sahip bir nesne.  
  
 *rglpszRegister*  
 Anahtarları ve anahtarlar için mevcut hiçbir değer bulunduğunda OLE sistem kayıt defterine eklenmesi değerleri temsil eden bir dize için işaretçiler dizisi.  
  
 *rglpszOverwrite*  
 Anahtarlar ve değerler var olan değerleri belirtilen anahtarları için kayıt defteri içeriyorsa, OLE sistem kayıt defterine eklenmesi temsil eden bir dize için işaretçiler dizisi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sunucu sınıfı başarıyla kaydedildi olursa sıfır dışı; Aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Uygulamaların çoğu kullanabilirsiniz `COleTemplateServer::Register` uygulamanın belge türleri kaydedilecek. Tipik bir düzen, uygulamanızın sistem kayıt defteri biçimi uygun değilse, kullanabileceğiniz `AfxOleRegisterServerClass` daha fazla denetim.  
  
 Kayıt defteri anahtarları ve değerleri içeren bir kümesinden oluşur. *RglpszRegister* ve *rglpszOverwrite* dizelerine dizileri bağımsız değişkenler, her oluşan bir anahtar veya değer tarafından ayrılmış bir **NULL** karakter ( `'\0'`). Bu dizelerin her biri olan yerlerde, karakter dizileri işaretlenmiş değiştirilebilir parametreler olabilir *%1* aracılığıyla *%5*.  
  
 Simgeler gibi doldurulur:  
  
|Sembol|Değer|  
|------------|-----------|  
|%1|Biçimlendirilmiş bir dize, sınıf kimliği|  
|%2|Sınıf adı|  
|%3|Yürütülebilir dosya yolu|  
|%4|Kısa bir tür adı|  
|%5|Uzun bir tür adı|  

### <a name="requirements"></a>Gereksinimler  
 **Üst bilgi**: afxdisp.h

##  <a name="afxoleseteditmenu"></a>  AfxOleSetEditMenu  
 Kullanıcı arabirimi uygulayan *typename* nesne komutu.  
  
```   
void AFXAPI AfxOleSetEditMenu(
    COleClientItem* pClient,  
    CMenu* pMenu,  
    UINT iMenuItem,  
    UINT nIDVerbMin,  
    UINT nIDVerbMax = 0,  
    UINT nIDConvert = 0); 
```  
  
### <a name="parameters"></a>Parametreler  
 *pClient*  
 İstemci OLE öğesini bir işaretçi.  
  
 *pMenu*  
 Güncelleştirilecek menü nesnesine bir işaretçi.  
  
 *iMenuItem*  
 Güncelleştirilecek menü öğesi dizini.  
  
 *nIDVerbMin*  
 Birincil fiil için karşılık gelen komut kimliği.  
  
 *nIDVerbMax*  
 Son fiil karşılık gelen komut kimliği.  
  
 *nIDConvert*  
 Dönüştürme menü öğesi kimliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Sunucu yalnızca birincil fiil tanıyorsa menü öğesi haline gelir "fiili *typename* nesne" ve *nIDVerbMin* komut, kullanıcı komutu seçtiğinde gönderilir. Sunucu çeşitli fiilleri tanır ve ardından menü öğesi olur, " *typename* nesne" ve kullanıcı komutu tıkladığında tüm fiiller listeleyen bir alt menü görünür. Menüden kullanıcı fiil seçtiğinde *nIDVerbMin* ilk fiili seçilmişse gönderilen *nIDVerbMin* + 1, ikinci fiili seçilen ve diğerleri ise gönderilir. Varsayılan `COleDocument` uygulaması, bu özellik otomatik olarak işler.  
  
 Aşağıdaki deyim, müşterinizin uygulama kaynak kodda olmalıdır (. RC) dosyası:  
  
 **#include \<afxolecl.rc >**  

### <a name="requirements"></a>Gereksinimler  
 **Üst bilgi**: afxole.h 

## <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md)

## <a name="afxoleunlockcontrol"></a> AfxOleUnlockControl
Sınıf üretecini belirtilen denetiminin kilidini açar.  
   
### <a name="syntax"></a>Sözdizimi  
```
BOOL AFXAPI AfxOleUnlockControl( REFCLSID clsid );  
BOOL AFXAPI AfxOleUnlockControl( LPCTSTR lpszProgID );  
```
### <a name="parameters"></a>Parametreler  
 *CLSID*  
 Denetim sınıfı benzersiz kimliği.  
  
 *lpszProgID*  
 Denetim programı benzersiz kimliği.  
   
### <a name="return-value"></a>Dönüş Değeri  
 Denetimin sınıf üreteci kilidi başarıyla açıldı olursa sıfır dışı; Aksi durumda 0.  
   
### <a name="remarks"></a>Açıklamalar  
 Bir denetim ile kilitli `AfxOleLockControl`, böylece denetimle ilişkili dinamik olarak oluşturulan veri bellekte kalır. Denetim olmayan oluşturulabilir ve görüntülendiğinde her zaman yok çünkü bu denetimin görünümünü önemli ölçüde hız kazandırabilir. Kontrol edilecek hazır olduğunuzda, çağrı `AfxOleUnlockControl`.  
   
### <a name="example"></a>Örnek  
```cpp
// Unlock control's (Microsoft Calendar Control) class factory.

AfxOleUnlockControl(_T("MSCAL.Calendar"));

```
   
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwin.h  
   
### <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları ve genel öğeleri](mfc-macros-and-globals.md)  
 [AfxOleLockControl](#afxolelockcontrol)

