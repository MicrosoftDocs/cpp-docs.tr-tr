---
description: 'Daha fazla bilgi edinin: TN064: ActiveX denetimlerinde Apartment-Model Iş parçacığı'
title: 'TN064: ActiveX Denetimlerinde Durum Modeli İş Parçacığı Oluşturma'
ms.date: 11/04/2016
helpviewer_keywords:
- OLE controls [MFC], container support
- containers [MFC], multithreaded
- TN064 [MFC]
- multithread container [MFC]
- apartment model threading [MFC]
ms.assetid: b2ab4c88-6954-48e2-9a74-01d4a60df073
ms.openlocfilehash: 977f429dfc7be6583f7021d1837caae15fca1495
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97214695"
---
# <a name="tn064-apartment-model-threading-in-activex-controls"></a>TN064: ActiveX Denetimlerinde Durum Modeli İş Parçacığı Oluşturma

> [!NOTE]
> Aşağıdaki teknik Not, çevrimiçi belgelere ilk eklenmesinden beri güncelleştirilmemiş. Sonuç olarak, bazı yordamlar ve konular güncel olmayabilir veya yanlış olabilir. En son bilgiler için çevrimiçi belge dizininde ilgilendiğiniz konuyu aramanız önerilir.

Bu teknik notta, ActiveX denetiminde apartman modeli iş parçacığı oluşturmayı nasıl etkinleştireceğinizi açıklanmaktadır. Apartman modeli iş parçacığı yalnızca Visual C++ sürüm 4,2 veya sonraki sürümlerde desteklenir.

## <a name="what-is-apartment-model-threading"></a>Apartment-Model Iş parçacığı nedir?

Apartman modeli, çok iş parçacıklı kapsayıcı uygulamasındaki ActiveX denetimleri gibi katıştırılmış nesneleri desteklemeye yönelik bir yaklaşımdır. Uygulamanın birden çok iş parçacığı olsa da, gömülü bir nesne örneği, yalnızca bir iş parçacığında yürütülecek bir "Apartment" öğesine atanır. Diğer bir deyişle, bir denetimin örneğine yapılan tüm çağrılar aynı iş parçacığında gerçekleşecektir.

Ancak, aynı denetim türünün farklı örnekleri farklı apartmanlarına atanabilir. Bu nedenle, bir denetimin birden çok örneği ortak (örneğin, statik veya genel veriler) herhangi bir veriyi paylaşıyorsa, bu paylaşılan verilere erişimin kritik bir bölüm gibi bir eşitleme nesnesi tarafından korunması gerekir.

Apartman iş parçacığı modeliyle ilgili tüm ayrıntılar için lütfen *OLE Programcı başvurusu*'ndaki [süreçler ve iş parçacıkları](/windows/win32/ProcThread/processes-and-threads) bölümüne bakın.

## <a name="why-support-apartment-model-threading"></a>Apartment-Model Iş parçacığı neden desteklenir

Apartman modeli iş parçacığı oluşturmayı destekleyen denetimler, aynı zamanda apartman modelini destekleyen çok iş parçacıklı kapsayıcı uygulamalarında kullanılabilir. Apartman modeli iş parçacığı etkinleştirmezseniz, denetiminizin kullanılabileceği olası kapsayıcılar kümesini sınırlandıracaksınız.

Özellikle çok az veya hiç paylaşılan veri yoksa, Grup modeli iş parçacığı, çoğu denetim için kolay bir şekilde etkinleştiriliyor.

## <a name="protecting-shared-data"></a>Paylaşılan verileri koruma

Denetiminiz statik üye değişkeni gibi paylaşılan verileri kullanıyorsa, verileri aynı anda birden fazla iş parçacığının değiştirmesini engellemek için bu verilere erişim kritik bir bölüm ile korunmalıdır. Bu amaçla kritik bir bölüm ayarlamak için, denetiminizin sınıfında bir statik üye değişkeni bildirin `CCriticalSection` . `Lock` `Unlock` Kodunuzun paylaşılan verilere eriştiği her yerde bu kritik bölüm nesnesinin ve üye işlevlerini kullanın.

Örneğin, tüm örnekler tarafından paylaşılan bir dizeyi sürdürmek için gereken bir denetim sınıfı düşünün. Bu dize statik bir üye değişkeninde korunabilir ve kritik bir bölüm tarafından korunabilir. Denetimin sınıf bildirimi şunları içerir:

```cpp
class CSampleCtrl : public COleControl
{
...
    static CString _strShared;
    static CCriticalSection _critSect;
};
```

Sınıfına yönelik uygulama, bu değişkenlerin tanımlarını içerir:

```cpp
int CString CSampleCtrl::_strShared;
CCriticalSection CSampleCtrl::_critSect;
```

`_strShared`Statik üyeye erişim daha sonra kritik bölüm tarafından korunabilir:

```cpp
void CSampleCtrl::SomeMethod()
{
    _critSect.Lock();
if (_strShared.Empty())
    _strShared = "<text>";
    _critSect.Unlock();

...
}
```

## <a name="registering-an-apartment-model-aware-control"></a>Grup modeli kullanan bir denetimi kaydetme

Apartman modeli iş parçacığı desteği olan denetimler *, sınıf kimliği* \\ **ınprocserver32** anahtarının altındaki sınıf kimliği kayıt defteri girişinde, "Apartment" adlı adlandırılmış değeri "Apartment" değerine ekleyerek kayıt defterindeki bu özelliği göstermelidir. Bu anahtarın denetiminizin otomatik olarak kaydedilmesini sağlamak için, altıncı parametresindeki *afxRegApartmentThreading* bayrağını şu şekilde geçirin `AfxOleRegisterControlClass` :

```cpp
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

Denetim projeniz, Visual C++ sürüm 4,1 veya sonraki sürümlerde ControlWizard tarafından oluşturulduysa, bu bayrak kodunuzda zaten mevcut olacaktır. İş parçacığı modelini kaydetmek için herhangi bir değişiklik yapılması gerekmez.

Projeniz ControlWizard 'ın önceki bir sürümü tarafından oluşturulduysa, mevcut kodunuzun altıncı parametre olarak bir Boole değeri olur. Var olan parametre TRUE ise, *afxRegInsertable | afxRegApartmentThreading* olarak değiştirin. Var olan parametre YANLıŞSA, *afxRegApartmentThreading* olarak değiştirin.

Denetiminiz, Apartman modeli iş parçacığı kurallarını izlemez, bu parametrede *afxRegApartmentThreading* ' i iletmemelidir.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye göre teknik notlar](../mfc/technical-notes-by-category.md)
