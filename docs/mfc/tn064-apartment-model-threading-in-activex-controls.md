---
title: 'TN064: Apartman modeli iş parçacığı ActiveX denetimlerinde'
ms.date: 11/04/2016
f1_keywords:
- vc.controls.activex
helpviewer_keywords:
- OLE controls [MFC], container support
- containers [MFC], multithreaded
- TN064 [MFC]
- multithread container [MFC]
- apartment model threading [MFC]
ms.assetid: b2ab4c88-6954-48e2-9a74-01d4a60df073
ms.openlocfilehash: d6f02b2106693226f6380e935a54e04e10d5b4f8
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57261173"
---
# <a name="tn064-apartment-model-threading-in-activex-controls"></a>TN064: Apartman modeli iş parçacığı ActiveX denetimlerinde

> [!NOTE]
>  Aşağıdaki Teknik Not çevrimiçi belgelere ilk eklenmiştir beri güncelleştirilmemiş. Eski veya yanlış sonuç olarak, bazı yordamlar ve konular olabilir. En son bilgiler için bu konuyu çevrimiçi belge dizininde arama önerilir.

Bu teknik Not apartman modeli iş parçacığı bir ActiveX denetimi içinde etkinleştirme açıklanmaktadır. Apartman modeli iş parçacığı oluşturma yalnızca Visual C++ 4.2 veya sonraki sürümlerinde desteklenmektedir.

## <a name="what-is-apartment-model-threading"></a>Apartman modeli iş parçacığı nedir

Apartman modeli iş parçacıklı kapsayıcılı bir uygulama içinde ActiveX denetimleri gibi katıştırılmış nesneleri destekleyen bir yaklaşımdır. Uygulama birden çok iş parçacığı sahip, ancak her bir nesnenin örneğini ", yalnızca bir iş parçacığında yürütülür bir bölme," atanır. Diğer bir deyişle, bir denetimin bir örneği yapılan tüm çağrıların aynı iş parçacığında gerçekleşir.

Ancak, farklı örnekleri aynı denetim türü için farklı apartmanlar atanabilir. Birden fazla denetimin ortak (örneğin, statik veya genel verileri) herhangi bir veri paylaşıyorsanız, bu nedenle, ardından bu paylaşılan verilere erişimi kritik bölümü gibi bir eşitleme nesnesi tarafından korunması gerekir.

Apartman modeli iş parçacığı oluşturma hakkında tam Ayrıntılar için lütfen bkz [işlemleri ve iş parçacıklarını](/windows/desktop/ProcThread/processes-and-threads) içinde *OLE Programcı Başvurusu*.

## <a name="why-support-apartment-model-threading"></a>Neden apartman modeli iş parçacığı oluşturma desteği

Apartman modeli iş parçacığı oluşturma desteği denetimleri apartman modeli de destekleyen birden çok iş parçacıklı kapsayıcı uygulamalarında kullanılabilir. Apartman modeli iş parçacığı etkinleştirmezseniz denetiminiz kullanılabilir kapsayıcıları olası kümesini sınırlayacaktır.

Apartman modeli iş parçacığı etkinleştirme özellikle çok az kayıpla veya paylaşılan veri varsa çoğu denetimler için kolay bir işlemdir.

## <a name="protecting-shared-data"></a>Paylaşılan veri koruma

Paylaşılan veri denetiminiz kullanıyorsa, statik üye değişkeni gibi verileri birden fazla iş parçacığı aynı anda verileri değiştirmesini önlemek için kritik bir bölüm ile korunmalıdır erişim sağlar. Bu amaç için önemli bir bölümünü ayarlamak için bir sınıfın statik üye değişkeni bildirme `CCriticalSection` denetiminizin sınıfında. Kullanım `Lock` ve `Unlock` Bu kritik bölüm üye işlevleri, kodunuzu Paylaşılan verilere erişen her yerde nesne.

, Örneğin, tüm örnekleri tarafından paylaşılan bir dize korumak için gereken bir denetim sınıf düşünün. Bu dize bir statik üye değişkeni saklanır ve önemli bir bölümü tarafından korunan. Denetimin sınıf bildirimi aşağıdakileri içerir:

```
class CSampleCtrl : public COleControl
{
...
    static CString _strShared;
    static CCriticalSection _critSect;
};
```

Sınıfı için uygulama bu değişkenler için tanımları içerir:

```
int CString CSampleCtrl::_strShared;
CCriticalSection CSampleCtrl::_critSect;
```

Erişim `_strShared` statik üye kritik bölümü tarafından ardından korunabilir:

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

## <a name="registering-an-apartment-model-aware-control"></a>Apartman modeli-algılayan bir denetimi kaydetme

Apartman modeli iş parçacığı oluşturma desteği denetimleri belirtmek bu özellik kayıt adlandırılmış değer "ThreadingModel" ekleyerek değerinde altında sınıfı kimliği kayıt defteri girdisini "Grup" ile *sınıf kimliği* \\ **Inprocserver32** anahtarı. Bu anahtar, denetim için otomatik olarak kaydedilecek neden geçirmek *afxRegApartmentThreading* altıncı parametresindeki bayrağı `AfxOleRegisterControlClass`:

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

Bu bayrak zaten denetim projenizi Visual c++ sürüm 4.1 veya üstünü ControlWizard tarafından üretilmişse, kodunuzda mevcut olacaktır. İş parçacığı modeli kaydetmek hiçbir değişiklik gereklidir.

Projenizi ControlWizard önceki bir sürümü tarafından üretilmişse, mevcut kodunuzu altıncı parametre olarak bir Boole değerine sahip olacaktır. Mevcut parametre TRUE ise değiştirmek *Afxregınsertable | afxRegApartmentThreading*. Mevcut parametre FALSE ise değiştirmek *afxRegApartmentThreading*.

Denetiminiz apartman modeli iş parçacığı kurallarını izlemiyorsa, değil geçmelidir *afxRegApartmentThreading* bu parametrede.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)
