---
title: "Çoklu iş parçacığı kullanımı: MFC 'de çalışan Iş parçacıkları oluşturma"
ms.date: 11/04/2016
helpviewer_keywords:
- multithreading [C++], worker threads
- background tasks [C++]
- threading [C++], worker threads
- worker threads [C++]
- threading [C++], creating threads
- threading [MFC], worker threads
- threading [C++], user input not required
ms.assetid: 670adbfe-041c-4450-a3ed-be14aab15234
ms.openlocfilehash: ab5b05b64ebcfbd6d15bd2229ee19d18fa7f919d
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77140508"
---
# <a name="multithreading-creating-worker-threads-in-mfc"></a>Çoklu iş parçacığı kullanımı: MFC 'de çalışan Iş parçacıkları oluşturma

Bir çalışan iş parçacığı genellikle kullanıcının uygulamanızı kullanmaya devam etmesi için beklemek zorunda olmaması gereken arka plan görevlerini işlemek için kullanılır. Yeniden hesaplama ve arka planda yazdırma gibi görevler, çalışan iş parçacıklarının iyi örnekleridir. Bu konuda, bir çalışan iş parçacığı oluşturmak için gereken adımlar ayrıntılı olarak açıklanmıştır. Konu başlıkları şunlardır:

- [İş parçacığı başlatılıyor](#_core_starting_the_thread)

- [Denetim işlevini uygulama](#_core_implementing_the_controlling_function)

- [Örnek](#_core_controlling_function_example)

Çalışan iş parçacığı oluşturma görece basit bir görevdir. İş parçacığın çalışmasını sağlamak için yalnızca iki adım gereklidir: denetim işlevini uygulama ve iş parçacığını başlatma. [CWinThread](../mfc/reference/cwinthread-class.md)öğesinden bir sınıf türetmek gerekli değildir. `CWinThread`özel bir sürümüne ihtiyacınız varsa bir sınıf türetebilirsiniz, ancak çoğu basit çalışan iş parçacığı için gerekli değildir. Değişiklik yapmadan `CWinThread` kullanabilirsiniz.

## <a name="_core_starting_the_thread"></a>Iş parçacığı başlatılıyor

`AfxBeginThread`aşırı yüklenmiş iki sürümü vardır: yalnızca çalışan iş parçacıkları ve Kullanıcı arabirimi iş parçacıklarını ve çalışan iş parçacıklarını oluşturabileceğiniz bir tane olabilir. İlk aşırı yüklemeyi kullanarak çalışan iş parçacığınız yürütmeye başlamak için, aşağıdaki bilgileri sağlayarak [AfxBeginThread](../mfc/reference/application-information-and-management.md#afxbeginthread)çağırın:

- Denetleyen işlevin adresi.

- Denetim işlevine geçirilecek parametre.

- Seçim İş parçacığının istenen önceliği. Varsayılan değer normal önceliktir. Kullanılabilir öncelik düzeyleri hakkında daha fazla bilgi için Windows SDK [SetThreadPriority](/windows/win32/api/processthreadsapi/nf-processthreadsapi-setthreadpriority) bölümüne bakın.

- Seçim İş parçacığı için istenen yığın boyutu. Varsayılan değer, oluşturma iş parçacığıyla aynı boyut yığınıdır.

- Seçim İş parçacığının askıya alınma durumunda oluşturulmasını istiyorsanız CREATE_SUSPENDED. Varsayılan değer 0 ' dır veya iş parçacığını normal olarak başlatır.

- Seçim İstenen güvenlik öznitelikleri. Varsayılan, üst iş parçacığıyla aynı erişimdir. Bu güvenlik bilgilerinin biçimi hakkında daha fazla bilgi için Windows SDK [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) bakın.

`AfxBeginThread`, sizin için bir `CWinThread` nesnesi oluşturup başlatır ve daha sonra başvurmak için adresini döndürür. Tüm nesnelerin düzgün şekilde serbest bırakıldığından emin olmak için, oluşturma yordamının tamamında denetimler yapılır

## <a name="_core_implementing_the_controlling_function"></a>Denetim Işlevini uygulama

Denetim işlevi iş parçacığını tanımlar. Bu işlev girildiğinde, iş parçacığı başlar ve çıktığında iş parçacığı sonlanır. Bu işlev aşağıdaki prototipe sahip olmalıdır:

```cpp
UINT MyControllingFunction( LPVOID pParam );
```

Parametresi tek bir değerdir. İşlevin bu parametre içinde aldığı değer, iş parçacığı nesnesi oluşturulduğunda oluşturucuya geçirilen değerdir. Denetim işlevi bu değeri, seçtiği her şekilde yorumlayabilir. Bir skaler değer veya birden çok parametre içeren bir yapının işaretçisi olarak kabul edilebilir veya yoksayılabilir. Parametresi bir yapıya başvuruyorsa, yapı yalnızca çağırandan iş parçacığına veri geçirmek için değil, aynı zamanda verileri iş parçacığından arayana geri geçirmek için de kullanılabilir. Verileri çağırana geri geçirmek için böyle bir yapı kullanırsanız, sonuçlar hazırlandığında iş parçacığının çağrıyı bilgilendirilmesi gerekir. Çalışan iş parçacığından arayana iletişim hakkında daha fazla bilgi için bkz. [Çoklu iş parçacığı kullanımı: programlama ipuçları](multithreading-programming-tips.md).

İşlev sonlandırıldığında, sonlandırma nedenini gösteren bir UINT değeri döndürmelidir. Genellikle, bu çıkış kodu farklı hata türlerini gösteren diğer değerlerle başarıyı göstermek için 0 ' dır. Bu, tamamen uygulamaya bağımlıdır. Bazı iş parçacıkları nesne kullanım sayılarını koruyabilir ve o nesnenin geçerli kullanım sayısını döndürebilir. Uygulamaların bu değeri nasıl alabileceği hakkında bilgi için bkz. [Çoklu Iş parçacığı kullanımı: Iş parçacıklarını sonlandırma](multithreading-terminating-threads.md).

MFC kitaplığı ile yazılmış çok iş parçacıklı programda yapabilecekleriniz için bazı kısıtlamalar vardır. Bu kısıtlamaların açıklamaları ve iş parçacıklarını kullanma hakkında diğer ipuçları için bkz. [Çoklu Iş parçacığı kullanımı: programlama ipuçları](multithreading-programming-tips.md).

## <a name="_core_controlling_function_example"></a>Işlev örneğini denetleme

Aşağıdaki örnek, bir denetim işlevinin nasıl tanımlanacağını ve bunu programın başka bir bölümünden nasıl kullanacağınızı gösterir.

```cpp
UINT MyThreadProc( LPVOID pParam )
{
    CMyObject* pObject = (CMyObject*)pParam;

    if (pObject == NULL ||
        !pObject->IsKindOf(RUNTIME_CLASS(CMyObject)))
    return 1;   // if pObject is not valid

    // do something with 'pObject'

    return 0;   // thread completed successfully
}

// inside a different function in the program
.
.
.
pNewObject = new CMyObject;
AfxBeginThread(MyThreadProc, pNewObject);
.
.
.
```

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

- [Çoklu İş Parçacığı Kullanımı: Kullanıcı Arabirimi İş Parçacıkları Oluşturma](multithreading-creating-user-interface-threads.md)

## <a name="see-also"></a>Ayrıca bkz.

[C++ ve MCF ile Çoklu İş Parçacığı Kullanımı](multithreading-with-cpp-and-mfc.md)
