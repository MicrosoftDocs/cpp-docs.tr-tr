---
title: "TN064: ActiveX denetimlerinde apartman modeli iş parçacığı oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.controls.activex
dev_langs: C++
helpviewer_keywords:
- OLE controls [MFC], container support
- containers [MFC], multithreaded
- TN064 [MFC]
- multithread container [MFC]
- apartment model threading [MFC]
ms.assetid: b2ab4c88-6954-48e2-9a74-01d4a60df073
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6298cba3dd411481fe912242a085595c02e129b7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="tn064-apartment-model-threading-in-activex-controls"></a>TN064: ActiveX Denetimlerinde Durum Modeli İş Parçacığı Oluşturma
> [!NOTE]
>  İlk çevrimiçi belgelerinde eklenmiştir beri aşağıdaki Teknik Not güncelleştirilmemiş. Sonuç olarak, bazı yordamlar ve konuları güncel veya yanlış olması olabilir. En son bilgiler için çevrimiçi belgeleri dizindeki ilgi konuyu aramak önerilir.  
  
 Bu teknik Not ActiveX denetiminde apartman modeli iş parçacığı oluşturma etkinleştirmek açıklanmaktadır. Apartman modeli iş parçacığı oluşturma yalnızca Visual C++ 4.2 veya sonraki sürümlerde desteklendiğini unutmayın.  
  
## <a name="what-is-apartment-model-threading"></a>Apartman modeli iş parçacığı oluşturma nedir  
 Apartman modeli destekleyen birden çok iş parçacıklı kapsayıcı uygulamadaki ActiveX denetimleri gibi katıştırılmış nesneler bir yaklaşımdır. Uygulamanın birden çok iş parçacığı açabilecek olsa da, her katıştırılmış bir nesnenin örneğine ", yalnızca bir iş parçacığı üzerinde yürütülür bir grup," atanır. Diğer bir deyişle, bir denetim örneği yapılan tüm çağrıların aynı iş parçacığı üzerinde gerçekleşir.  
  
 Ancak, aynı tür denetimi farklı örnekleri için farklı grupların atanabilir. Bir denetim birden çok örneğini ortak (örneğin, statik veya genel verileri) herhangi bir veri paylaşıyorsanız, bu nedenle, sonra bu paylaşılan verilere erişimi önemli bir bölümü gibi bir eşitleme nesnesi tarafından korunması gerekir.  
  
 Apartman modeli iş parçacığı oluşturma hakkında tam bilgi için lütfen bkz. [işlemleri ve iş parçacıklarını](http://msdn.microsoft.com/library/windows/desktop/ms684841) içinde *OLE Programcı Başvurusu*.  
  
## <a name="why-support-apartment-model-threading"></a>Neden apartman modeli iş parçacığı oluşturma desteği  
 Apartman modeli iş parçacığı oluşturma desteği denetimleri de Grup modelini destekleyen birden çok iş parçacıklı kapsayıcı uygulamalarda kullanılabilir. Apartman modeli iş parçacığı oluşturma etkinleştirmezseniz denetiminizi kullanılabilir kapsayıcıları olası kümesini sınırlar.  
  
 Apartman modeli iş parçacığı oluşturma etkinleştirme özellikle çok az kayıpla veya hiç paylaşılan veri varsa çoğu denetimler için kolay bir işlemdir.  
  
## <a name="protecting-shared-data"></a>Paylaşılan veri koruma  
 Paylaşılan veri denetiminizi kullanıyorsa, statik üye değişkeni gibi verileri birden çok iş parçacığı aynı anda verileri değiştirmesini önlemek için önemli bir bölümü ile korunması gereken erişim sağlar. Bu amaç için önemli bir bölümünü ayarlamak için bir statik üye değişkeni sınıfının bildirme `CCriticalSection` denetiminizin sınıfında. Kullanım `Lock` ve **Unlock** kritik bu bölümün üye işlevleri, kodunuzu Paylaşılan verilere erişen her yerde nesne.  
  
 , Örneğin, tüm örnekleri tarafından paylaşılan bir dize korumak için gereken bir denetim sınıfı göz önünde bulundurun. Bu dize bir statik üye değişkeni korunur ve önemli bir bölümü tarafından korumalı. Denetimin sınıf bildirimi aşağıdakileri içerir:  
  
```  
class CSampleCtrl : public COleControl  
{  
 ...  
    static CString _strShared;  
    static CCriticalSection _critSect;  
};  
```  
  
 Sınıfı için uygulama bu değişkenleri tanımlarında aşağıdakileri içerir:  
  
```  
int CString CSampleCtrl::_strShared;  
CCriticalSection CSampleCtrl::_critSect;  
```  
  
 Erişim `_strShared` statik üye kritik bölümü tarafından sonra korunabilir:  
  
```  
void CSampleCtrl::SomeMethod()  
{  
    _critSect.Lock();
if (_strShared.Empty())  
    _strShared = "<text>";  
    _critSect.Unlock();

 ...  
}  
```  
  
## <a name="registering-an-apartment-model-aware-control"></a>Apartman modeli kullanmayan denetimi kaydetme  
 Apartman modeli iş parçacığı oluşturma desteği denetimleri belirtmek Bu yetenek kayıt adlandırılmış değeri "ThreadingModel" ekleyerek değerinde altında sınıfı kimliği kayıt defteri girdisini "Grup" ile *sınıf kimliği* \\ **Inprocserver32** anahtarı. Bu anahtar, denetim için otomatik olarak kaydedilecek neden olmak için geçmesi `afxRegApartmentThreading` altıncı parametrenin bayrağı `AfxOleRegisterControlClass`:  
  
```  
BOOL CSampleCtrl::CSampleCtrlFactory::UpdateRegistry(BOOL bRegister)  
{  
    if (bRegister)  
    return AfxOleRegisterControlClass(
    AfxGetInstanceHandle(), 
    m_clsid, 
    m_lpszProgID, 
    IDS_SAMPLE, 
    IDB_SAMPLE, 
    afxRegApartmentThreading, 
    _dwSampleOleMisc, 
    _tlid, 
    _wVerMajor, 
    _wVerMinor);

 else  
    return AfxOleUnregisterClass(m_clsid,
    m_lpszProgID);

}  
```  
  
 Denetim projenizi ControlWizard Visual c++ 4.1 veya sonraki bir sürümü tarafından oluşturulmuşsa bu bayrak zaten kodunuzda mevcut olacaktır. İş parçacığı modelini kaydettirmek hiçbir değişiklik gereklidir.  
  
 Projeniz ControlWizard önceki bir sürümü tarafından oluşturulmuşsa, mevcut kodunuzu altıncı parametre bir Boole değeri gerekir. Varolan parametresi TRUE ise, değiştirmek `afxRegInsertable | afxRegApartmentThreading`. Var olan parametre FALSE ise, değiştirmek `afxRegApartmentThreading`.  
  
 Denetim apartman modeli iş parçacığı oluşturma kuralları izlemiyorsa değil, geçmelidir `afxRegApartmentThreading` bu parametrede.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)   
 [Kategoriye göre teknik notlar](../mfc/technical-notes-by-category.md)

