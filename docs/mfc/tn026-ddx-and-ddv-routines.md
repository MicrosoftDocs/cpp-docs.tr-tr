---
title: 'TN026: DDX ve DDV rutinleri | Microsoft Docs'
ms.custom: ''
ms.date: 06/28/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- DDX
- DDV
dev_langs:
- C++
helpviewer_keywords:
- DDX (dialog data exchange), procedures
- TN026
- DDV (dialog data validation), procedures
ms.assetid: c2eba87a-4b47-4083-b28b-e2fa77dfb4c4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3930f08ae0708b81dde218a88fcda4dc34931390
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46389745"
---
# <a name="tn026-ddx-and-ddv-routines"></a>TN026: DDX ve DDV Rutinleri

> [!NOTE]
> Aşağıdaki Teknik Not çevrimiçi belgelere ilk eklenmiştir beri güncelleştirilmemiş. Eski veya yanlış sonuç olarak, bazı yordamlar ve konular olabilir. En son bilgiler için bu konuyu çevrimiçi belge dizininde arama önerilir.

Bu Not, iletişim kutusu veri değişimi (DDX) ve iletişim kutusu veri doğrulama (DDV) mimarisi açıklanmaktadır. Ayrıca, nasıl DDX_ veya DDV_ yordamı yazdığınızı ve ClassWizard, yordamları kullanmak için nasıl genişletebileceğinizi açıklar.

## <a name="overview-of-dialog-data-exchange"></a>İletişim kutusu veri değişimi genel bakış

Tüm iletişim kutusu veri işlevleri, C++ kodu ile gerçekleştirilir. Özel kaynaklar veya Sihirli makroları yoktur. Bir iletişim kutusu veri değişimi mu her iletişim kutusu sınıfında geçersiz kılınan sanal işlev ve doğrulama mekanizması kalbidir. Her zaman bu formda de bulunur:

```cpp
void CMyDialog::DoDataExchange(CDataExchange* pDX)
{
    CDialog::DoDataExchange(pDX);   // call base class

    //{{AFX_DATA_MAP(CMyDialog)
        <data_exchange_function_call>
        <data_validation_function_call>
    //}}AFX_DATA_MAP
}
```

Özel biçim AFX açıklamaları ClassWizard bulun ve bu işlev içindeki kod düzenlemek izin verin. ClassWizard ile uyumlu olmayan kod dışında özel biçim açıklamaları yerleştirilmelidir.

Yukarıdaki örnekte, \<data_exchange_function_call > şu şekildedir:

```cpp
DDX_Custom(pDX, nIDC, field);
```

ve \<data_validation_function_call > isteğe bağlıdır ve şu şekildedir:

```cpp
DDV_Custom(pDX, field, ...);
```

Birden fazla DDX_/DDV_ çifti her eklenebilir `DoDataExchange` işlevi.

'Afxdd_.h' iletişim kutusu veri değişimi rutinleri ve MFC ile sağlanan iletişim kutusu veri doğrulama rutinleri listesi için bkz.

İletişim verisi olduğundan bunu: üye verileri `CMyDialog` sınıfı. Bir yapı veya benzer bir şey depolanmaz.

## <a name="notes"></a>Notlar

Bu "iletişim kutusu veri" dediğimiz olsa da, tüm özellikler türetilen sınıfta kullanılabilir `CWnd` ve sadece iletişim kutularına atanacağı sınırlı değildir.

İlk veri değerlerinin standart C++ oluşturucuda, genellikle bir bloğu ile ayarlanır `//{{AFX_DATA_INIT` ve `//}}AFX_DATA_INIT` yorumlar.

`CWnd::UpdateData` başlatma ve hata işleme çağrısı etrafında işlemdir `DoDataExchange`.

Çağırabilirsiniz `CWnd::UpdateData` veri değişimi ve doğrulaması gerçekleştirmek için herhangi bir zamanda. Varsayılan olarak `UpdateData`(TRUE), varsayılan olarak adlandırılır `CDialog::OnOK` işleyicisi ve `UpdateData`(FALSE), varsayılan olarak adlandırılır `CDialog::OnInitDialog`.

DDV_ yordamı hemen DDX_ yordamı için izlemelidir *alan*.

## <a name="how-does-it-work"></a>Nasıl çalışır

İletişim kutusu veri kullanmak için aşağıdakileri anlamanız gerekmez. Ancak, bu planda nasıl çalıştığını anlamak kendi exchange veya doğrulama yordamı yazmanıza yardımcı olur.

`DoDataExchange` Üye işlevi olan çok benzer `Serialize` üye işlev - bu, alma veya verileri ayarlama/dış formundan sorumlu (Bu durumda denetleyen bir iletişim kutusunda) / sınıf üyesi verilerine. *PDX* parametre veri alışverişi yapmak için bağlam ve benzer `CArchive` parametresi `CObject::Serialize`. *PDX* (bir `CDataExchange` nesnesi) bayrak çok benzer bir yöne sahip `CArchive` yön bayrağı vardır:

- Varsa `!m_bSaveAndValidate`, ardından veri durumu denetimlere yükleyebilirsiniz.

- Varsa `m_bSaveAndValidate`, ardından veri durumu denetimleri ayarlayın.

Doğrulama yalnızca oluşur, `m_bSaveAndValidate` ayarlanır. Değerini `m_bSaveAndValidate` BOOL parametresi tarafından belirlenir `CWnd::UpdateData`.

Var olan üç diğer ilginç `CDataExchange` üyeleri:

- `m_pDlgWnd`: Denetimler içeren pencere (genellikle iletişim). 'This' geçirmek DDX_ ve DDV_ genel işlevleri arayanlar önlemek için her DDX/DDV yordamına budur.

- `PrepareCtrl`, ve `PrepareEditCtrl`: bir iletişim denetimi için veri değişimi hazırlar. Odağı ayarlamak için bir doğrulama başarısız olursa, bu denetimin tanıtıcı depolar. `PrepareCtrl` Düzen olmayan denetimler için kullanılan ve `PrepareEditCtrl` düzenleme denetimleri için kullanılır.

- `Fail`: Giriş hatası kullanıcıya uyarı bir ileti kutusu getirme sonra çağrılır. Bu yordam için son denetim odağı geri yükler (son çağrı `PrepareCtrl` veya `PrepareEditCtrl`) ve bir özel durum. Bu üye işlevi DDX_ hem DDV_ rutinleri çağrılabilir.

## <a name="user-extensions"></a>Kullanıcı Uzantıları

Varsayılan DDX/DDV mekanizmasını genişletmek için birkaç yolu vardır. Şunları yapabilirsiniz:

- Yeni veri türleri ekleyin.

    ```cpp
    CTime
    ```

- Yeni exchange yordamlar (DDX_) ekleyin.

    ```cpp
    void PASCAL DDX_Time(CDataExchange* pDX, int nIDC, CTime& tm);
    ```

- Yeni doğrulama yordamları (DDV_) ekleyin.

    ```cpp
    void PASCAL DDV_TimeFuture(CDataExchange* pDX, CTime tm, BOOL bFuture);
    // make sure time is in the future or past
    ```

- Rastgele ifadeler için doğrulama yordamlarını geçirin.

    ```cpp
    DDV_MinMax(pDX, age, 0, m_maxAge);
    ```

    > [!NOTE]
    > Rastgele tür ifadeleri ClassWizard tarafından düzenlenemez ve bu nedenle dışında özel biçim yorumları taşınacağını (/ / {{AFX_DATA_MAP(CMyClass)).

Sahip `DoDialogExchange` üye işlevi koşullular veya tüm diğer geçerli C++ deyimleri ile karıştırılmış değişimi ve doğrulaması işlev çağrılarını içerir.

```cpp
//{{AFX_DATA_MAP(CMyClass)
DDX_Check(pDX, IDC_SEX, m_bFemale);
DDX_Text(pDX, IDC_EDIT1, m_age);
//}}AFX_DATA_MAP
if (m_bFemale)
    DDV_MinMax(pDX, age, 0, m_maxFemaleAge);
else
    DDV_MinMax(pDX, age, 0, m_maxMaleAge);
```

> [!NOTE]
> Yukarıda gösterildiği gibi bu tür kod ClassWizard tarafından düzenlenemez ve yalnızca özel biçim yorumları dışında kullanılmalıdır.

## <a name="classwizard-support"></a>ClassWizard desteği

ClassWizard, kendi DDX_ ve DDV_ yordamlarını ClassWizard kullanıcı arabirimi ile tümleştirmenize olanak tanıyarak DDX/DDV özelleştirmeleri kümesini destekler. Bir proje veya pek çok proje belirli DDX ve DDV rutinleri yeniden kullanmayı planlıyorsanız Bunun yapılması yalnızca yararlı maliyetidir.

Bunu yapmak için özel girişleri DDX içinde gerçekleştirilir. CLW (Visual C++'ın önceki sürümlerini depolanan bu bilgiler APSTUDIO. INI) veya projenizin. CLW dosyası. Özel girişleri olabilir ya da [genel bilgisi] bölümünde projenizin girildi. CLW dosya veya DDX [ExtraDDX] bölümünde. \Program Studio\Visual Visual C ++ \bin dizinine dosyasında CLW. DDX oluşturmanız gerekebilir. Zaten mevcut değilse CLW dosyası. Özel DDX_/DDV_ yordamları yalnızca bir belirli projesinde kullanmayı planlıyorsanız, girişler projenizin [genel bilgisi] bölümüne ekleyin. Bunun yerine CLW dosya. Birçok projelerde rutinleri kullanmayı planlıyorsanız, girişleri DDX [ExtraDDX] bölümünü ekleyin. CLW.

Bu özel girişleri genel biçimi şöyledir:

> ExtraDDXCount =*n*

Burada *n* ExtraDDX sayısı? biçiminin izleyebilecekleri satırları

> ExtraDDX? =*anahtarları*; *vb-keys*; *istemi*; *türü*; *initValue*; *DDX_Proc* [; *DDV_Proc*; *prompt1*; *arg1* [; *prompt2*; *fmt2*]]

nerede? 1 - bir sayıdır *n* tanımlanıyorsa listesinde hangi DDX türünü belirten.

Her alanın bir ';' karakteriyle ayrılır. Alanlar ve bunların amacı, aşağıda açıklanmıştır.

- *anahtarları*

  Bu değişken türü hangi iletişim kutusu denetimleri için izin verilen gösteren tek karakterleri içeren bir liste.

  |Karakter|İzin verilen denetimi|
  |-|-|
  E | Düzenle
  C | iki durum onay kutusu
  c | üç durum onay kutusu
  R | bir gruptaki ilk radyo düğmesi
  L | nonsorted liste kutusu
  l | Sıralı liste kutusu
  M | Birleşik giriş kutusu (ile öğeyi düzenleme)
  N | nonsorted bırakma listesi
  n | sıralanmış bırakma listesi
  1. | DDX ekleme listesi gidin eklenip eklenmeyeceğini (kuyruk için varsayılan Ekle) Bu genellikle 'Denetim' özelliği aktarım DDX rutinleri için kullanılır.

- *vb-keys*

  Bu alan yalnızca 16-bit üründe VBX denetimleri (VBX denetimler 32-bit üründe desteklenmiyor) için kullanılır.

- *istemi*

  Özellik birleşik giriş kutusu içinde (tırnak işareti gerekmez) yerleştirmek için dize

- *Türü*

  Üstbilgi dosyasında yayacak tek tanımlayıcısı. Bizim örneğimizde DDX_Time ile bu CTime için ayarlanır.

- *vb-keys*

  Bu sürümünde kullanılmaz ve her zaman boş olmalıdır

- *initValue*

  İlk değer: 0 veya boş. Boş ise, hiçbir başlatma satırı uygulama dosyasının //{{AFX_DATA_INIT bölümünde yazılır. C++ nesneleri için boş bir girişi kullanılmalıdır (gibi `CString`, `CTime`ve benzeri) sahip olan doğru başlatma garanti oluşturucular.

- *DDX_Proc*

  DDX_ yordamı tek tanımlayıcısı. C++ işlev adı "İle DDX_" başlamalıdır, ancak "DDX_" dahil değildir \<DDX_Proc > tanımlayıcısı. Yukarıdaki örnekte \<DDX_Proc > tanımlayıcısı zaman olur. ClassWizard işlevi çağrısı v souboru implementace yazdığında {{AFX_DATA_MAP bölümünde, bu ekler bu ad için DDX_, bu nedenle DDX_Time ulaşan.

- *Açıklama*

  Bu DDX değişkenle için iletişim kutusu göstermek için bir açıklama. DDX/DDV çifti tarafından gerçekleştirilen işlem tanımlar burada ve genellikle bir şey sağlamak istediğiniz metni yerleştirin.

- *DDV_Proc*

  Giriş DDV kısmı isteğe bağlıdır. Tüm DDX yordamları karşılık gelen DDV rutinleri vardır. Genellikle, doğrulama aşamasını aktarımı ayrılmaz bir parçası dahil etmek daha uygundur. Herhangi bir parametre DDV alışkanlık gerektirmeyen ClassWizard DDV rutinleri hiçbir parametre olmadan desteklemediğinden bu genellikle durumdur.

- *bağımsız değişken*

  DDV_ yordamı tek tanımlayıcısı. C++ işlev adı "DDV_" ile başlamalıdır, ancak "DDX_" eklemeyin \<DDX_Proc > tanımlayıcısı.

  *arg* 1 veya 2 DDV args tarafından izlenir:

   - *promptN*

     Düzenleme öğesi (ile & Hızlandırıcı için) yukarıda yerleştirmek için dize.

   - *fmtN*

     Biçim karakteri biri bağımsız değişken türü için:

     |Karakter|Tür|
     |-|-|
     d | int
     u | unsigned int
     D | long int (diğer bir deyişle, uzun)
     U | işaretsiz uzun (DWORD)
     F | float
     F | çift
     s | dize

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)
