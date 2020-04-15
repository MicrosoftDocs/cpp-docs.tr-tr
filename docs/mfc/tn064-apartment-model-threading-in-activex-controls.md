---
title: 'TN064: ActiveX Denetimlerinde Durum Modeli İş Parçacığı Oluşturma'
ms.date: 11/04/2016
helpviewer_keywords:
- OLE controls [MFC], container support
- containers [MFC], multithreaded
- TN064 [MFC]
- multithread container [MFC]
- apartment model threading [MFC]
ms.assetid: b2ab4c88-6954-48e2-9a74-01d4a60df073
ms.openlocfilehash: 0c6a42124b4b2b03ae7cd9277fa14d43eac7a2bb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366066"
---
# <a name="tn064-apartment-model-threading-in-activex-controls"></a>TN064: ActiveX Denetimlerinde Durum Modeli İş Parçacığı Oluşturma

> [!NOTE]
> Aşağıdaki teknik not, çevrimiçi belgelere ilk olarak eklenmediğinden beri güncelleştirilemedi. Sonuç olarak, bazı yordamlar ve konular güncel veya yanlış olabilir. En son bilgiler için, çevrimiçi belge dizini ilgi alanı için arama nız önerilir.

Bu teknik not, ActiveX denetiminde daire modeli iş parçacığının nasıl etkinleştirilen açıklanmaktadır. Daire modeli iş parçacığının yalnızca Visual C++ sürümleri 4.2 veya sonraki sürümlerde desteklenerek desteklendirileni unutmayın.

## <a name="what-is-apartment-model-threading"></a>Daire-Model Diş İşi Nedir

Daire modeli, çok iş parçacığı kapsayıcı uygulaması içinde ActiveX denetimleri gibi gömülü nesneleri desteklemeye bir yaklaşımdır. Uygulama birden çok iş parçacığı olsa da, katıştırılmış nesnenin her örneği yalnızca bir iş parçacığı üzerinde yürütülecek bir "daire" atanır. Başka bir deyişle, denetim örneğine yapılan tüm çağrılar aynı iş parçacığı üzerinde gerçekleşir.

Ancak, aynı tür denetimfarklı örnekleri farklı daireleratanabilir. Bu nedenle, bir denetimin birden çok örneği ortak (örneğin, statik veya genel veriler) herhangi bir veriyi paylaşıyorsa, bu paylaşılan verilere erişimin kritik bir bölüm gibi bir eşitleme nesnesi tarafından korunması gerekir.

Daire iş parçacığı modeli hakkında ayrıntılı bilgi için, Lütfen *OLE Programcısıreferansındaki* [İşlemler ve İş Parçacıkları'na](/windows/win32/ProcThread/processes-and-threads) bakın.

## <a name="why-support-apartment-model-threading"></a>Neden Destek Daire-Model Threading

Daire modeli iş parçacığı destekleyen denetimler, daire modelini de destekleyen çok iş parçacığı kapsayıcı uygulamalarında kullanılabilir. Daire modeli iş parçacığı etkinleştirmezseniz, denetiminizin kullanılabildiği olası kapsayıcı kümesini sınırlandırmış olursunuz.

Daire modeli iş parçacığı etkinleştirme, özellikle çok az veya hiç paylaşılan veri varsa, çoğu denetimler için kolaydır.

## <a name="protecting-shared-data"></a>Paylaşılan Verileri Koruma

Denetiminiz statik üye değişken gibi paylaşılan verileri kullanıyorsa, birden fazla iş parçacığının verileri aynı anda değiştirmesini önlemek için bu verilere erişim kritik bir bölümle korunmalıdır. Bu amaçla kritik bir bölüm ayarlamak için, denetiminizin sınıfında `CCriticalSection` statik bir üye değişken bildirin. Kodunuzun paylaşılan verilere eriştisiğü bu kritik bölüm nesnesinin `Lock` ve `Unlock` üye işlevlerini kullanın.

Örneğin, tüm örnekler tarafından paylaşılan bir dize yi koruması gereken bir denetim sınıfı düşünün. Bu dize statik bir üye değişkende tutulabilir ve kritik bir bölüm tarafından korunabilir. Denetimin sınıf bildirimi aşağıdakileri içerir:

```cpp
class CSampleCtrl : public COleControl
{
...
    static CString _strShared;
    static CCriticalSection _critSect;
};
```

Sınıf için uygulama bu değişkenler için tanımlar içerecektir:

```cpp
int CString CSampleCtrl::_strShared;
CCriticalSection CSampleCtrl::_critSect;
```

`_strShared` Statik üyeye erişim daha sonra kritik bölüm tarafından korunabilir:

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

## <a name="registering-an-apartment-model-aware-control"></a>Daire-Model-Farkında Kontrol Kayıt

Daire modeli iş parçacığı destekleyen denetimler sınıf *kimliği*\\**InprocServer32** anahtarı altında kendi sınıf kimlik kayıt defteri girişinde "Daire" değeri ile adlandırılmış değeri "ThreadingModel" ekleyerek, kayıt defterinde bu yeteneği göstermelidir. Bu anahtarın otomatik olarak kontrolünüz için kaydedilmesine neden olmak için, altıncı parametredeki *afxRegApartmentThreading* bayrağını şu şekilde `AfxOleRegisterControlClass`geçirin:

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

Denetim projeniz Visual C++ sürüm 4.1 veya sonraki sürümlerde ControlWizard tarafından oluşturulduysa, bu bayrak zaten kodunuzda bulunur. İş parçacığı modelini kaydetmek için değişiklik gerekmez.

Projeniz ControlWizard'ın önceki bir sürümü tarafından oluşturulduysa, varolan kodunuz altıncı parametre olarak Boolean değerine sahip olur. Mevcut parametre TRUE ise, *afxRegInsertable | afxRegApartmentThreading değiştirin.* Varolan parametre FALSE ise, *afxRegApartmentThreading olarak değiştirin.*

Denetiminiz apartman modeli iş parçacığı için kurallara uymuyorsa, bu parametrede *afxRegApartmentThreading'i* geçmemelisiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)
