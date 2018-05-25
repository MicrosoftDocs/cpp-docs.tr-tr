---
title: Yazma ve kod (C++) yeniden düzenlemesi | Microsoft Docs
ms.custom: ''
ms.date: 04/30/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 56ffb9e9-514f-41f4-a3cf-fd9ce2daf3b6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 000428ce3975dab108387ddb598bddf4a89fcfdd
ms.sourcegitcommit: da7b7533d1a4dc141cc0f09149e4e4196f2fe329
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/23/2018
---
# <a name="writing-and-refactoring-code-c"></a>Yazma ve yeniden düzenleme kod (C++)

Visual C++ kod düzenleyicisini ve IDE birçok kodlama yardımları sağlar. Bazı C++ için benzersiz ve bazı temelde tüm Visual Studio diller için aynıdır. Paylaşılan özellikler hakkında daha fazla bilgi için bkz: [kod ve Metin Düzenleyici'de kod yazma](/visualstudio/ide/writing-code-in-the-code-and-text-editor). Etkinleştirme ve C++ özgü özellikleri yapılandırmak için seçenekleri altında bulunur **Araçları &#124; seçenekleri &#124; metin düzenleyici &#124; C/C++**. Ayarlamak istediğiniz hangi seçeneği seçtikten sonra daha fazla yardım tuşlarına basarak alabilirsiniz **F1** iletişim odakta olduğunda. Biçimlendirme seçeneklerini genel kodunu yazın `Editor C++` içine **Hızlı Başlat**.

İçinde bulunan olabilir veya Visual Studio, gelecekteki bir sürümüne dahil edilmeyen Deneysel özellikleri [metin düzenleyici C++ Experimental](/visualstudio/ide/reference/options-text-editor-c-cpp-experimental) iletişim. Visual Studio 2017 içinde etkinleştirmeniz **Tahmine dayalı IntelliSense** bu iletişim.

## <a name="adding-new-files"></a>Yeni dosyaları ekleme

Yeni dosyalar için bir proje eklemek için Çözüm Gezgini'nde proje düğümüne sağ tıklayın ve seçin **Ekle &#124; yeni**.

## <a name="formatting-options"></a>Biçimlendirme seçenekleri

Biçimlendirme girintileri, küme parantezi tamamlama ve renklendirme gibi seçenekleri ayarlamak için "Biçimlendirme C++" yazdığınız **Hızlı Başlat** penceresi. Visual Studio 2017 15.7 ve sonraki sürümleri ClangFormat destekler. İçinde yapılandırabilirsiniz [C/C++ biçimlendirme özellik sayfası](/visualstudio/ide/reference/options-text-editor-c-cpp-formatting) altında **Araçları &#124; seçenekleri &#124; metin düzenleyici &#124; C/C++ &#124; biçimlendirme**.

![C++ biçimlendirme seçenekleri](media/cpp-formatting-options.png)

## <a name="intellisense"></a>IntelliSense

IntelliSense üyeleri, türleri ve işlev aşırı yüklemelerinin hakkında satır içi bilgi sağlayan özellikleri kümesi adıdır. Aşağıdaki çizimde yazarken görüntülenen üye listesi açılır gösterir. Seçili öğeyi metin kodu dosyanıza girmek için SEKME tuşuna basabilirsiniz.

![C&#43; &#43; üye listesi açılır](../ide/media/vs2015_cpp_statement_completion.png "vs2015_cpp_statement_completion")

Tam bilgi için bkz: [Visual C++ IntelliSense](/visualstudio/ide/visual-cpp-intellisense).

## <a name="insert-snippets"></a>Kod parçacıkları Ekle

Bir kod parçacığında, kaynak kodu önceden tanımlanmış bir parçasıdır. Tek bir nokta ya da bir parçacığını eklemek ya da kod parçacığını seçili metinle surround için seçili metnin sağ tıklayın. Seçili deyimiyle surround için üç adım aşağıda gösterilmiştir bir döngü için. Son görüntüde sarı vurgular SEKME tuşu ile erişim düzenlenebilir alanlardır. Daha fazla bilgi için bkz: [kod parçacıkları](/visualstudio/ide/code-snippets).

![Visual C&#43; &#43; Ekle parçacığı bırakma&#45;aşağı](../ide/media/vs2015_cpp_surround_with.png "vs2015_cpp_surround_with")

## <a name="add-class"></a>Sınıf ekleme

Yeni bir sınıf ekleyin **proje** sınıfı Sihirbazı'nı kullanarak menüsü.

![Visual C yeni sınıf ekleyin&#43;&#43;](../ide/media/vs2015_cpp_add_class.png "vs2015_cpp_add_class")

Sınıf Sihirbazı, değiştirmek veya varolan bir sınıfa incelemek için de kullanabilirsiniz.

![Visual C&#43; &#43; sınıfı Sihirbazı](../ide/media/vs2015_cpp_class_wizard.png "vs2015_cpp_class_wizard")

Daha fazla bilgi için bkz: [işlevsellik ekleme kodu sihirbazlar (C++) ile](../ide/adding-functionality-with-code-wizards-cpp.md).

## <a name="refactoring"></a>Yeniden Düzenle

Yapan yeniden düzenlemeler hızlı eylem bağlam menüsü altında veya tıklayarak mevcut bir [ampul](/visualstudio/ide/perform-quick-actions-with-light-bulbs) Düzenleyicisi'nde.  Bazı de bulunan **Düzenle > yeniden düzenlemeniz** menüsü.  Bu özellikler şunlardır:

* [Yeniden Adlandır](refactoring/rename.md)
* [İşlevi Ayıkla](refactoring/extract-function.md)
* [Saf Sanalları Uygula](refactoring/implement-pure-virtuals.md)
* [Bildirim / Tanım Oluştur](refactoring/create-declaration-definition.md)
* [Move İşleminin Tanımı](refactoring/move-definition-location.md)
* [Ham Dize Sabit Değerine Dönüştür](refactoring/convert-to-raw-string-literal.md)
* [İmzayı Değiştir](refactoring/change-signature.md)

## <a name="navigate-and-understand"></a>Gidin ve anlama

Visual C++ kodu Gezinti özelliklerinin diğer dilleri ile paylaşır. Daha fazla bilgi için bkz: [gezinme kodu](/visualstudio/ide/navigating-code) ve [kodunu yapısı görüntüleme](/visualstudio/ide/viewing-the-structure-of-code).

## <a name="quickinfo"></a>Quıckınfo

Tür bilgilerini görmek için bir değişken gelin.

![Visual C&#43; &#43; Quıckınfo](../ide/media/vs2015_cpp_quickinfo.png "vs2015_cpp_quickInfo")

## <a name="open-document-navigate-to-header"></a>Açık belge (üstbilgi Git)

Üstbilgi adını sağ tıklayın bir `#include` yönergesi ve üst bilgi dosyasını açın.

![Visual C&#43; &#43; açık belge menü seçeneği](../ide/media/vs2015_cpp_open_document.png "vs2015_cpp_open_document")

## <a name="peek-definition"></a>Özet tanımı

Bir değişken veya işlev bildirimi, sağ tıklatın, sonra vurgulu seçin **Peek tanımı** tanımına satır içi görünümünü görmek için. Daha fazla bilgi için bkz: [Peek tanımı (Alt + F12)](/visualstudio/ide/how-to-view-and-edit-code-by-using-peek-definition-alt-plus-f12).

![Visual C&#43; &#43; Peek tanımı](../ide/media/vs2015_cpp_peek_definition.png "vs2015_cpp_peek_definition")

## <a name="go-to-definition"></a>Tanıma gitme

Bir değişken veya işlev bildirimi, sağ tıklatın, sonra vurgulu seçin **Tanıma Git** nesne tanımlandığı belgeyi açmak için.

## <a name="view-call-hierarchy"></a>Çağrı hiyerarşisini görüntüleme

Herhangi bir işlev çağrısına sağ tıklayın ve çağırır tüm işlevleri ve bunu tüm işlevleri resursive listesini görüntüleyin. Listedeki her işlevi aynı şekilde genişletilebilir. Daha fazla bilgi için bkz: [çağrı hiyerarşisi](/visualstudio/ide/reference/call-hierarchy).

![Visual C&#43; &#43; çağrı hiyerarşisi](../ide/media/vs2015_cpp_call_hierarchy.png "vs2015_cpp_call_hierarchy")

## <a name="toggle-header--code-file"></a>Geçiş üstbilgi / kod dosyası

Sağ tıklatın ve seçin **geçiş üstbilgi / kod dosyası** geri ve İleri üstbilgi dosyası ve onun ilişkili kod dosyası arasında geçiş yapmak için.

## <a name="outlining"></a>Anahat Oluşturma

Herhangi bir kaynak kodu dosyasına sağ tıklayın ve seçin **anahat** daraltın veya tanımları ve/veya yalnızca ilgilendiğiniz bölümleri Gözat kolaylaştırmak için özel bölgeler genişletin. Daha fazla bilgi için bkz: [anahat](/visualstudio/ide/outlining).

![Visual C&#43; &#43; anahat oluşturma](../ide/media/vs2015_cpp_outlining.png "vs2015_cpp_outlining")

## <a name="scrollbar-map-mode"></a>ScrollBar eşleme modu

ScrollBar eşleme modu, hızla kaydırın ve kod dosyası aracılığıyla geçerli konumunuz ayrılmadan Gözat olanak sağlar. Veya bu konuma doğrudan gitmek için kod Haritası herhangi bir yere tıklayın. Daha fazla bilgi için bkz: [nasıl yapılır: scrollbar özelleştirerek kodunuzu izlemek](/visualstudio/ide/how-to-track-your-code-by-customizing-the-scrollbar).

![Kod Haritası Visual c&#43;&#43;](../ide/media/vs2015_cpp_code_map.png "vs2015_cpp_code_map")

## <a name="generate-graph-of-include-files"></a>Dosyaları Ekle Grafiği Oluştur

Bir kod dosyası projenize sağ tıklayın ve seçin **dosyaları Ekle Generate grafiği** hangisinin dosyaları diğer dosyalar tarafından eklenir bir grafik görmek için.

![Visual C&#43; &#43; dosyaları Ekle grafiği](../ide/media/vs2015_cpp_include_graph.png "vs2015_cpp_include_graph")

## <a name="f1-help"></a>F1 Yardımı

İmleç üzerinde veya herhangi bir tür, anahtar sözcüğü veya işlevi hemen sonra yerleştirin ve docs.microsoft.com üzerinde doğrudan ilgili başvuru konusu gitmek için F1 tuşuna basın. F1 hata listesinde ve birçok iletişim kutularındaki öğeler üzerinde de çalışır.

## <a name="quick-launch"></a>Hızlı Başlat

Kolayca herhangi bir pencere veya Visual Studio aracında gitmek için yalnızca kullanıcı arabirimini sağ üst köşesindeki hızlı başlatma penceresinde adını yazın. Siz yazarken otomatik tamamlama listesini filtreler.

![Visual Studio hızlı başlatma](../ide/media/vs2015_cpp_quick_launch.png "vs2015_cpp_quick_launch")
