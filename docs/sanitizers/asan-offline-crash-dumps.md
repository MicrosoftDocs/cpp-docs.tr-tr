---
title: Addresstemizleme bulutu veya dağıtılmış test
description: Visual Studio ve Azure için Addresstemizleme özelliği genişletildi
ms.date: 03/02/2021
helpviewer_keywords:
- AddressSanitizer cloud or distributed testing
ms.openlocfilehash: 53bbb1ca04a5c4636914591cf10bfcc6bf275d42
ms.sourcegitcommit: 6ed44d9c3fb32e965e363b9c69686739a90a2117
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2021
ms.locfileid: "102470818"
---
# <a name="addresssanitizer-cloud-or-distributed-testing"></a>Addresstemizleme bulutu veya dağıtılmış test

Adrestemizleme hatalarında ve nerede oluştuğunda hata ayıklamanıza gerek yoktur. Çalışma zamanını, bir hata oluştuğunda tüm Addresstemizler 'e özgü bağlamı depolayan bir kilitlenme dökümü oluşturacak şekilde yapılandırın. Daha sonra bu kilitlenme dökümünü hata ayıklama için başka bir BILGISAYARA gönderin. Çevrimdışı hata ayıklama, bulutta veya dağıtılmış testlerde Addresstemizlenebilir çalışırken kritik bir zaman koruyucu olabilir. Hatanın gerçekleştiği test veya üretim altyapısında döküm oluşturabilir ve daha sonra geliştirici BILGISAYARıNıZDA hata ayıklaması yapabilirsiniz.

Visual Studio hata ayıklayıcı kesin olarak tanılanan Addresstemizleme hataları sağlar. Testleri yeniden çalıştırmak, çok büyük veri kümelerini kopyalamak, kayıp verileri bulmak veya çevrimdışı olan test makinelerini bulmak zorunda kalmadan bu hataları görüntüleyebilirsiniz. Yalnızca kilitlenme dökümünü yüklemeniz gerekir.

Kilitlenme dökümü, aşağıdaki ortam değişkeni ayarlanarak Addresstemizleme hatalarıyla oluşturulmuştur:

`set ASAN_SAVE_DUMPS=MyFileName.dmp`

> [!NOTE]
> *`.dmp`* Visual Studio adlandırma kurallarını izlemek için dosya adının bir sonekine sahip olması gerekir.

Bu [döküm dosyası](/previous-versions/windows/desktop/proc_snap/export-a-process-snapshot-to-a-file) , başka bir makinede daha sonraki bir tarihte Visual Studio kullanılarak görüntülenebilir.

Visual Studio, hata bilgilerini özgün kaynak kodu bağlamında gösterebilir. Bunu yapmak için, Visual Studio [hata ayıklama sembolleri](/windows/win32/dxtecharts/debugging-with-symbols) ve [dizinli kaynak kodu](/windows-hardware/drivers/debugger/source-indexing)gerektirir. En iyi hata ayıklama deneyimi için, bu ikilileri üretmek için kullanılan EXE, PDB ve kaynak kodu eşleşmelidir.

Kaynakları ve sembolleri depolama hakkında daha fazla bilgi için [kaynak ve semboller](#source) bölümüne bakın. Uygulama ayrıntıları ve ayrıntılı denetim hakkında bilgi için bkz. [hata ayıklayıcı tümleştirmesi](asan-debugger-integration.md).

## <a name="example---build-test-and-analyze"></a>Örnek-oluşturma, test etme ve çözümleme

Üç makineyi göz önünde bulundurun: A, B ve C. derlemeler B makinesinde yapılır, testler C makinesinde çalıştırılır ve A makinesindeki sorunları analiz edersiniz. Hatalar, kaynak kodunuzda kaynak satıra ve sütun numaralarına göre raporlanır. [Kaynak kodunun tam sürümü](#source)KULLANıLARAK oluşturulan PDB dosyasındaki bir sembol kümesiyle birlikte çağrı yığınını görebilirsiniz.

Aşağıdaki adımlar, bir. dmp dosyası oluşturulmasına yol açabilecek yerel veya dağıtılmış senaryolar ve bu Addresstemizleme döküm dosyasını çevrimdışı görüntülemek için kullanılır.

### <a name="produce-a-dmp-locally"></a>Yerel olarak bir. dmp üretme

- Oluşturma
- Yürütülebilir dosyayı test etme
- Oluşturulan bir. dmp dosyasını yapı dizinine kopyalayın
- . Dmp dosyasını eşleştirilmiş. pdb ile aynı dizinde açın

### <a name="produce-a-dmp-on-a-distributed-system"></a>Dağıtılmış bir sistemde. dmp üretme

- [Kaynak dizini oluşturma veri blokları](/windows/win32/debug/source-server-and-source-indexing) için pdb oluşturma ve [sonrasında işlem sonrası](#source)
- (. Exe,. pdb) atomik çiftini test makinesine kopyalayın ve testleri çalıştırın
- Hata raporlama veritabanına (. pdb,. dmp) atomik çiftlerini yazma
- Visual Studio, aynı dizinde eşleştirilmiş. pdb ile bir. dmp dosyası açar

> [!NOTE]
> Analiz için kullandığınız Visual Studio 2019 makinesi GitHub 'a veya *`\\Machine\share`* dizini oluşturulmuş kaynağınızın depolandığı dahili konuma erişebilmelidir.

## <a name="view-addresssanitizer-dmp-files"></a>Adres Temizleme. dmp dosyalarını görüntüle

1. Hata ayıklayıcı IDE 'nin PDB ve kaynak dosyalarınızı bulabileceği şekilde emin olun.

1. Visual Studio 'Yu açın ve **kod olmadan devam et**' i seçin. Dosya Aç   >    >  iletişim kutusunu açmak için Dosya Aç **Dosya** ' yı seçin. Dosya adı sonekinin **. dmp** olduğundan emin olun.

   :::image type="content" source="./media/asan-open-crash-dump-file.png" alt-text="Visual Studio 'da dosya açma Dosya menüsünün ekran görüntüsü.":::

   Burada gösterilen ekranda, simgelere ve kaynağa IDE erişimi sağlamak için bir adım daha gerekir.

1. Sembol yollarını ayarlayın ve ardından **yalnızca yerelle hata ayıkla**' yı seçin.

   :::image type="content" source="./media/asan-dump-file-open.png" alt-text="Visual Studio 'da mini döküm Özeti ekranının ekran görüntüsü.":::

Bu ekran görüntüsünde, kaynak ve Addresstemizleme meta verilerinin yüklendiği son yüklenen döküm dosyası gösterilir.

:::image type="content" source="./media/asan-view-crash-metadata.png" alt-text="Kaynak dosyalarını ve Addresstemizleme meta verilerini gösteren hata ayıklayıcının ekran görüntüsü.":::

## <a name="source-and-symbols"></a><a name="source"></a> Kaynak ve semboller

Kaynak sunucu, bir istemcinin bir uygulama oluşturmak için kullanılan kaynak dosyaların **tam sürümünü** almasına olanak tanır. Yürütülebilir bir dosya veya DLL için kaynak kodu zaman içinde değişebilir ve sürümler arasında değişiklik yapabilir. Bu uygulamayı, uygulamanın belirli bir sürümünü oluşturan aynı kaynak koduna bakmak için kullanabilirsiniz.

Bir EXE dosyasının PDB dosyası ile hata ayıklaması yaparken, hata ayıklayıcı kaynak denetiminden uygun dosyaları almak için katıştırılmış kaynak sunucu veri bloğunu kullanabilir. Derleyici seçeneği tarafından PDB 'ye otomatik olarak yerleştirilen tam adlarla eşlenen dosyaları yükler **`/Zi`** .

Kaynak sunucuyu kullanmak için, *`pdbstr.exe`* pdb dosyanıza bir veri bloğu yazmak üzere kullanılarak uygulamanın "kaynak dizini oluşturulmuş" olması gerekir `srcsrv` . Daha fazla bilgi için [kaynak sunucunun ve kaynak dizin oluşturmanın](/windows/win32/debug/source-server-and-source-indexing)veri bloğu bölümüne bakın. [Kaynakları dizin oluşturma ve sembolleri yayımlama adımlarını](/azure/devops/pipelines/tasks/build/index-sources-publish-symbols) ve [hata ayıklayıcı için sembolleri ve kaynak kodu nasıl belirttireceğiz](/visualstudio/debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger) de bulacaksınız.

Dış belgeler için bkz.:

- [Git ile kaynak dizini oluşturma](https://gist.github.com/baldurk/c6feb31b0305125c6d1a)
- [Daha kolay hata ayıklama Kılavuzu](https://www.codeproject.com/articles/115125/source-indexing-and-symbol-servers-a-guide-to-easi)
- [Kaynak dizin oluşturma işlemi kullanılmıyor awesomeness](https://randomascii.wordpress.com/2011/11/11/source-indexing-is-underused-awesomeness/)

## <a name="see-also"></a>Ayrıca bkz.

[Addresstemizme genel bakış](./asan.md)\
[Adrestemizleme bilinen sorunlar](./asan-known-issues.md)\
[Addresstemizleyebilir derleme ve dil başvurusu](./asan-building.md)\
[Addresstemizleme çalışma zamanı başvurusu](./asan-runtime.md)\
[Addresstemizleme gölge baytları](./asan-shadow-bytes.md)\
[Addresstemizleme hata ayıklayıcısı tümleştirmesi](./asan-debugger-integration.md)\
[Addresstemizleme hatası örnekleri](./asan-error-examples.md)
