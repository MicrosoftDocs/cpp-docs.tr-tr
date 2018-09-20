---
title: 'Nasıl yapılır: (C++) derleme sırasında kaynak ekleme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vs.resvw.resource.including
- vc.resvw.resource.including
dev_langs:
- C++
helpviewer_keywords:
- comments [C++], compiled files
- resources [C++], including at compile time
- projects [C++], including resources
- '#include directive'
- include directive (#include)
ms.assetid: 357e93c2-0a29-42f9-806f-882f688b8924
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0ed41f7025b3564ab05fe13e77d3e9400cd0f385
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46420237"
---
# <a name="how-to-include-resources-at-compile-time"></a>Nasıl Yapılır: Derleme Sırasında Kaynak Ekleme

Normalde tüm kaynaklar bir kaynak betiği (.rc) dosyasında varsayılan düzenini çalışmak daha kolay olur. Ancak, kaynaklar diğer dosyalar geçerli projenizi derleme zamanında bunları listeleyerek ekleyebilirsiniz **derleme zamanı yönergeleri** kutusunda [kaynak içerikleri iletişim kutusu](../windows/resource-includes-dialog-box.md).

Ana .rc dosyasının farklı bir dosyadaki kaynakları yerleştirmek için birkaç nedeni vardır:

- .Rc dosyasını kaydederken, silinecek değil kaynak deyimleri için yorum eklemek için.

   Kaynak düzenleyicileri .rc doğrudan okunmaz veya `resource.h` dosyaları. Kaynak Derleyicisi bunları kaynak düzenleyicileri tarafından tüketilen .aps dosyalarına derlenir. Bu dosya, bir derleme adımdır ve yalnızca sembolik verileri depolar. (Örneğin, açıklamalar) sembolik değil bilgi işlem ile normal bir derleme olarak derleme işlemi sırasında göz ardı edilir. .Rc dosyasıyla .aps dosyası zaman uyumsuz olarak alır her .rc dosyası yeniden oluşturuldu (kaydettiğinizde, örneğin, kaynak düzenleyicisini .rc dosyasının üzerine yazar ve `resource.h` dosyası). Herhangi bir değişiklik kaynaklardaki .rc dosyasına eklenen kalır ancak .rc dosyasının üzerine sonra açıklamalar her zaman kaybolacak.

- Zaten geliştirdiğinizde ve test kaynakları içerecek şekilde ve daha fazla değişiklik gerekmez. (Dahil edilir, ancak bir .rc uzantısı yoksa tüm dosyaları kaynak düzenleyicileri tarafından düzenlenebilir olmayacaktır.)

- Birkaç farklı proje tarafından kullanılmakta olan veya, bir kaynak kod sürüm denetimi sisteminin bir parçası olan ve bu nedenle değişiklikleri tüm projeleri burada etkiler, merkezi bir konumda bulunmalıdır kaynakları dahil etmektir.

- Özel bir biçimde kaynakları (örneğin, RCDATA kaynaklar) içerecek şekilde. RCDATA kaynaklar özel gereksinimlerine sahip olabilir. Örneğin, bir ifade Nameıd alan için bir değer olarak kullanamazsınız. Daha fazla bilgi için Windows SDK belgelerine bakın.

Bölümler Bu koşullardan biri karşılaması, var olan bir .rc dosyası varsa, biri bölümlerde yerleştirmeniz gerekir veya daha fazla ayrı .rc dosyaları ve bunları kullanarak projenize dahil [kaynak içerikleri iletişim kutusu](../windows/resource-includes-dialog-box.md). *Projectname*.rc2 dosya yeni bir proje \res alt dizinde oluşturulur, bu amaçla kullanılır.

### <a name="to-include-resources-in-your-project-at-compile-time"></a>Kaynakları projenizde, derleme zamanında dahil etmek için

1. Benzersiz bir dosya adı ile kaynak betik dosyasını kaynakları yerleştirin. Kullanmayın *projectname*.rc, çünkü bu ana kaynak betik dosyası için kullanılan dosya adı.

2. .Rc dosyasına sağ tıklayın (içinde [kaynak görünümü](../windows/resource-view-window.md)) seçip **kaynak içerikleri** kısayol menüsünden.

3. İçinde **derleme zamanı yönergeleri** kutusunda [#include](../preprocessor/hash-include-directive-c-cpp.md) ana kaynak dosyasıyla geliştirme ortamındaki yeni kaynak dosyası eklemek için derleyici yönergesi.

   Bu şekilde dahil dosyalarındaki kaynaklar, yürütülebilir dosya, derleme zamanında yapılır. Projenizin ana .rc dosyası üzerinde çalışırken bunlar doğrudan düzenlemek veya değişiklik için kullanılabilir değildir. Ayrı olarak eklenen .rc dosyası açmanız gerekir. Dahil edilir, ancak bir .rc uzantısı yoksa tüm dosyaları kaynak düzenleyicileri tarafından düzenlenebilir olmayacaktır.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[Kaynak dosyaları](../windows/resource-files-visual-studio.md)<br/>
[Kaynak Düzenleyicileri](../windows/resource-editors.md)