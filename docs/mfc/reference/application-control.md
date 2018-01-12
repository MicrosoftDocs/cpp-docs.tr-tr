---
title: Uygulama denetimi | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.mfc.macros
dev_langs: C++
helpviewer_keywords: application control [MFC]
ms.assetid: c1f69f15-e0fe-4515-9f36-d63d31869deb
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c055f5489c7b85f5f974256709451426b614db47
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="application-control"></a>Uygulama Denetimi
OLE uygulamaları ve bunların nesneler üzerinde önemli denetim gerektirir. OLE sistem DLL'leri başlatma ve uygulamaları otomatik olarak bırakın, kendi üretim ve nesneleri değiştirilmesini koordine ve benzeri kurabilmesi gerekir. Bu konudaki işlevleri bu gereksinimleri karşılar. OLE sistem DLL'leri tarafından çağrılan ek olarak, bu işlevler, bazen de uygulamalar tarafından çağrılmalıdır. 
  
### <a name="application-control"></a>Uygulama Denetimi  
  
|||  
|-|-|  
|[AfxOleCanExitApp](#afxolecanexitapp)|Uygulama sonlandırabilir olup olmadığını gösterir.|  
|[AfxOleGetMessageFilter](#afxolegetmessagefilter)|Uygulamanın geçerli ileti filtresini alır.|  
|[AfxOleGetUserCtrl](#afxolegetuserctrl)|Geçerli kullanıcı denetimi bayrağı alır.|  
|[AfxOleSetUserCtrl](#afxolesetuserctrl)|Ayarlar veya kullanıcı denetimi bayrağını temizler.|  
|[AfxOleLockApp](#afxolelockapp)|Framework'ün genel bir uygulamada etkin nesne sayısı sayısını artırır.|  
|[AfxOleLockControl](#afxolelockcontrol)| Belirtilen denetiminin üreteci kilitler. |
|[AfxOleUnlockApp](#afxoleunlockapp)|Azaltır framework'ün sayısı etkin bir uygulama nesnelerin sayısı.| 
|[AfxOleUnlockControl](#afxoleunlockcontrol)| Belirtilen denetiminin üreteci kilidini açar. |
|[AfxOleRegisterServerClass](#afxoleregisterserverclass)|Bir sunucu OLE sistem kayıt defterine kaydeder.|  
|[AfxOleSetEditMenu](#afxoleseteditmenu)|İçin kullanıcı arabirimi uygulayan *typename* nesne komutu.|  

  
##  <a name="afxolecanexitapp"></a>AfxOleCanExitApp  
 Uygulama sonlandırabilir olup olmadığını gösterir.  
  
```   
BOOL AFXAPI AfxOleCanExitApp(); 
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Uygulama çıkarsanız, sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Nesnelerini bekleyen başvurular varsa bir uygulama sonlanmalıdır değil. Genel işlevler `AfxOleLockApp` ve `AfxOleUnlockApp` artırmak ve sırasıyla bir sayaç uygulamanın nesnelere başvurular azaltma. Bu sayaç sıfır olduğunda uygulama sonlanmalıdır değil. Sayaç sıfır değilse, kullanıcının sistem menüsünden veya Dosya menüsünden Çıkış Kapat seçtiğinde uygulamanın ana penceresi (değil yok) gizlenir. Bu işlev framework çağrıları **CFrameWnd::OnClose**.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCAutomation#2](../../mfc/codesnippet/cpp/application-control_1.cpp)]  

## <a name="requirements"></a>Gereksinimler  
 **Üstbilgi**: afxdisp.h 

##  <a name="afxolegetmessagefilter"></a>AfxOleGetMessageFilter  
 Uygulamanın geçerli ileti filtresini alır.  
  
```   
COleMessageFilter* AFXAPI AfxOleGetMessageFilter(); 
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli İleti Filtresi için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Geçerli erişmek için bu işlevi çağırmak `COleMessageFilter`-yalnızca çağırırdı gibi türetilen nesnesini, `AfxGetApp` geçerli uygulama nesneye erişim.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCAutomation#3](../../mfc/codesnippet/cpp/application-control_2.cpp)]  
  
 [!code-cpp[NVC_MFCAutomation#4](../../mfc/codesnippet/cpp/application-control_3.cpp)]  

### <a name="requirements"></a>Gereksinimler  
 **Üstbilgi**: afxwin.h 

##  <a name="afxolegetuserctrl"></a>AfxOleGetUserCtrl  
 Geçerli kullanıcı denetimi bayrağı alır.  
  
```   
BOOL AFXAPI AfxOleGetUserCtrl(); 
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kullanıcı uygulamayı denetiminde ise sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanıcı açıkça açıldığında veya yeni bir belge oluşturulan kullanıcı uygulama denetiminde değil. Uygulama DLL'leri OLE sistem tarafından başlatılan değil kullanıcı da denetiminde ise — diğer bir deyişle, kullanıcı uygulama sistemi kabuğu ile başlatılan durumunda.  

### <a name="requirements"></a>Gereksinimler  
 **Üstbilgi**: afxdisp.h

##  <a name="afxolesetuserctrl"></a>AfxOleSetUserCtrl  
 Başvuru için açıklandığı kullanıcı denetimi bayrağını ayarlar veya temizler `AfxOleGetUserCtrl`.  
  
```  
void AFXAPI AfxOleSetUserCtrl(BOOL bUserCtrl); 
```  
  
### <a name="parameters"></a>Parametreler  
 *bUserCtrl*  
 Kullanıcı denetimi bayrağı ayarlanmış temizlenmiş veya olup olmadığını belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Belge olmayan olduğunda veya yüklenen bir kapsayıcı uygulamasından katıştırılmış nesne yükleme gibi dolaylı bir işlem aracılığıyla oluşturulan framework kullanıcı oluşturduğunda veya bir belgeyi yükler, ancak bu işlevi çağırır.  
  
 Diğer Eylemler, uygulamanızda kullanıcı uygulama denetiminde yerleştirileceği bu işlevi çağırır.  

### <a name="requirements"></a>Gereksinimler  
 **Üstbilgi**: afxdisp.h

##  <a name="afxolelockapp"></a>AfxOleLockApp  
 Framework'ün genel uygulama etkin nesnelerin sayısı sayısını artırır.  
  
```   
void AFXAPI AfxOleLockApp(); 
```  
  
### <a name="remarks"></a>Açıklamalar  
 Framework nesneleri sayısını bir uygulamada etkin tutar. `AfxOleLockApp` Ve `AfxOleUnlockApp` İşlevler, sırasıyla artırmak ve bu sayı azaltma.  
  
 Kullanıcı çalıştığında etkin nesneleri olan bir uygulamayı kapatmak — etkin nesneler sayısı olduğu sıfır olmayan bir uygulama — tamamen kapanma yerine kullanıcının görünümünden uygulama framework gizler. `AfxOleCanExitApp` İşlevi uygulama sonlandırabilir olup olmadığını gösterir.  
  
 Çağrı `AfxOleLockApp` bir istemci uygulaması tarafından hala kullanılmakta çalışırken yok edilmesi bu nesne için istenmeyen olacaksa, OLE arabirimleri kullanıma sunan herhangi bir nesneden. Ayrıca `AfxOleUnlockApp` yıkıcı çağrıları herhangi bir nesnenin içinde `AfxOleLockApp` oluşturucuda. Varsayılan olarak, `COleDocument` (ve türetilmiş sınıfları) otomatik olarak Kilitle ve uygulama kilidini açın.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCAutomation#5](../../mfc/codesnippet/cpp/application-control_4.cpp)]  

### <a name="requirements"></a>Gereksinimler  
 **Üstbilgi**: afxdisp.h

##  <a name="afxoleunlockapp"></a>AfxOleUnlockApp  
 Azaltır framework'ün uygulamadaki etkin nesne sayısı.  
  
```   
void AFXAPI AfxOleUnlockApp(); 
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: `AfxOleLockApp` daha fazla bilgi için.  
  
 Etkin nesne sayısı sıfır ulaştığında **AfxOleOnReleaseAllObjects** olarak adlandırılır.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [AfxOleLockApp](#afxolelockapp).  

### <a name="requirements"></a>Gereksinimler  
 **Üstbilgi**: afxdisp.h  

 ## <a name="afxolelockcontrol"></a>AfxOleLockControl
Denetimle ilişkili dinamik olarak oluşturulan veri bellekte kalır için belirtilen denetiminin üreteci kilitler.  
   
### <a name="syntax"></a>Sözdizimi    
```
BOOL AFXAPI AfxOleLockControl(  REFCLSID clsid  );  
BOOL AFXAPI AfxOleLockControl( LPCTSTR lpszProgID );  
```
### <a name="parameters"></a>Parametreler  
 `clsid`  
 Denetimin benzersiz sınıf kimliği.  
  
 `lpszProgID`  
 Denetimin benzersiz program kimliği.  
   
### <a name="return-value"></a>Dönüş Değeri  
 Denetimin sınıf üreticisi başarıyla kilitlediyseniz sıfır olmayan; Aksi takdirde 0.  
   
### <a name="remarks"></a>Açıklamalar  
 Bu denetimlerin görünümünü önemli ölçüde hızlandırılabilir. Örneğin, sonra bir iletişim kutusunda bir denetim oluşturma ve denetimle kilitlemek `AfxOleLockControl`, oluşturma ve iletişim kutusunda gösterilen ya da yok her zaman yeniden KILL gerekmez. Kullanıcı açar ve sürekli olarak bir iletişim kutusu kapanır, denetimlerinizi kilitleme performansı önemli ölçüde artırabilir. Denetim yok etmek hazır olduğunuzda, çağrı `AfxOleUnlockControl`.  
   
### <a name="example"></a>Örnek  
```cpp
// Starts and locks control's (Microsoft Calendar) class factory. 
// Control will remain in memory for lifetime of
// application or until AfxOleUnlockControl() is called.

AfxOleLockControl(_T("MSCAL.Calendar"));
```
   
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** < afxwin.h >  
   
### <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları ve genel öğeleri](mfc-macros-and-globals.md)   
 [AfxOleUnlockControl](#afxoleunlockcontrol)
 
##  <a name="afxoleregisterserverclass"></a>AfxOleRegisterServerClass  
 Bu işlev sunucunuz OLE sistem kayıt defterinde kaydetmenizi sağlar.  
  
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
 `clsid`  
 Sunucunun OLE sınıfı kimliği başvurusu  
  
 `lpszClassName`  
 Sunucu nesneleri sınıf adını içeren bir dize işaretçi.  
  
 *lpszShortTypeName*  
 Sunucunun nesne türünün "Grafiği." gibi kısa adını içeren bir dize işaretçi  
  
 *lpszLongTypeName*  
 "Microsoft Excel 5.0 grafiği." gibi sunucunun nesnesi türü uzun adını içeren bir dize işaretçi  
  
 `nAppType`  
 Alınan bir değer **OLE_APPTYPE** OLE uygulama türünü belirleyen numaralandırması. Olası değerler şunlardır:  
  
- `OAT_INPLACE_SERVER`Sunucu tam sunucu kullanıcı arabirimi sahiptir.  
  
- `OAT_SERVER`Sunucusu yalnızca katıştırma destekler.  
  
- `OAT_CONTAINER`Kapsayıcı eklerinin bağlantılarını destekler.  
  
- `OAT_DISPATCH_OBJECT``IDispatch`-özellikli nesne.  
  
 `rglpszRegister`  
 Anahtarları ve anahtarlar için var olan hiçbir değer bulunursa OLE sistem kayıt defterine eklenecek değerleri temsil eden dizeleri işaretçiler dizisi.  
  
 `rglpszOverwrite`  
 Anahtarları ve var olan değerleri belirtilen anahtarları için kayıt defteri içeriyorsa, OLE sistem kayıt defterine eklenecek değerleri temsil eden dizeleri işaretçiler dizisi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sunucu sınıfı başarıyla kaydedildi, sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Çoğu uygulamayı kullanabilirsiniz **COleTemplateServer::Register** uygulamanın belge türlerinin kaydetmek için. Uygulamanızın sistem kayıt defteri biçimi tipik bir düzen sığmadığında kullanabileceğiniz `AfxOleRegisterServerClass` daha fazla denetim için.  
  
 Kayıt defteri anahtarları ve değerleri kümesinden oluşur. `rglpszRegister` Ve `rglpszOverwrite` dizeleri işaretçiler dizileri bağımsız değişkenler, her oluşan bir anahtar veya değer tarafından ayrılmış bir **NULL** karakter ( `'\0'`). Bu dizelerin her biri, yerler karakter sıraları ile işaretlenmiş değiştirilebilir parametreler olabilir `%1` aracılığıyla `%5`.  
  
 Simgeler gibi doldurulmuştur:  
  
|Simgesi|Değer|  
|------------|-----------|  
|%1|Dize olarak biçimlendirilmiş sınıf kimliği|  
|%2|Sınıf adı|  
|%3|Yürütülebilir dosyasının yolu|  
|%4|Kısa türü adı|  
|%5|Uzun türü adı|  

### <a name="requirements"></a>Gereksinimler  
 **Üstbilgi**: afxdisp.h

##  <a name="afxoleseteditmenu"></a>AfxOleSetEditMenu  
 İçin kullanıcı arabirimi uygulayan *typename* nesne komutu.  
  
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
 `pClient`  
 İstemci OLE öğesi için bir işaretçi.  
  
 `pMenu`  
 Güncelleştirilecek menü nesnesine bir işaretçi.  
  
 *iMenuItem*  
 Güncelleştirilecek menü öğesi dizini.  
  
 `nIDVerbMin`  
 Birincil fiil karşılık gelen komut kimliği.  
  
 *nIDVerbMax*  
 Son fiili karşılık gelen komut kimliği.  
  
 *nIDConvert*  
 Dönüştürme menü öğesi için kimliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Yalnızca birincil fiil sunucusunun tanıdığı menü öğesi olur "fiil *typename* nesne" ve `nIDVerbMin` komutu kullanıcı komutu seçtiğinde gönderilir. Birkaç fiiller sunucusunun tanıdığı sonra menü öğesi olur " *typename* nesne" ve kullanıcı komutu seçtiğinde tüm fiiller listeleyen bir alt belirir. Kullanıcı menüden fiil seçtiğinde `nIDVerbMin` ilk fiil seçilir gönderilen `nIDVerbMin` + 1 ikinci fiili seçilen ve diğerleri ise gönderilir. Varsayılan `COleDocument` uygulaması, bu özelliği otomatik olarak yönetir.  
  
 Aşağıdaki deyim, istemcinin uygulama kaynak kodda olmalıdır (. RC) dosyası:  
  
 **#include \<afxolecl.rc >**  

### <a name="requirements"></a>Gereksinimler  
 **Üstbilgi**: afxole.h 

## <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md)

## <a name="afxoleunlockcontrol"></a>AfxOleUnlockControl
Belirtilen denetiminin üreteci kilidini açar.  
   
### <a name="syntax"></a>Sözdizimi  
  ```
BOOL AFXAPI AfxOleUnlockControl( REFCLSID clsid );  
BOOL AFXAPI AfxOleUnlockControl( LPCTSTR lpszProgID );  
```
### <a name="parameters"></a>Parametreler  
 `clsid`  
 Denetimin benzersiz sınıf kimliği.  
  
 `lpszProgID`  
 Denetimin benzersiz program kimliği.  
   
### <a name="return-value"></a>Dönüş Değeri  
 Denetimin sınıf üreticisi başarıyla kullanıma açıldı, sıfır olmayan; Aksi takdirde 0.  
   
### <a name="remarks"></a>Açıklamalar  
 Bir denetim ile kilitli `AfxOleLockControl`, böylece denetimle ilişkili dinamik olarak oluşturulan veri bellekte kalır. Denetim olmayan oluşturulabilir ve görüntüleneceğini her zaman yok olduğundan bu denetimin görünümünü önemli ölçüde hızlandırabilir. Denetim yok etmek hazır olduğunuzda, çağrı `AfxOleUnlockControl`.  
   
### <a name="example"></a>Örnek  
 ```cpp
// Unlock control's (Microsoft Calendar Control) class factory.

AfxOleUnlockControl(_T("MSCAL.Calendar"));

```
   
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** < afxwin.h >  
   
### <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları ve genel öğeleri](mfc-macros-and-globals.md)  
 [AfxOleLockControl](#afxolelockcontrol)

