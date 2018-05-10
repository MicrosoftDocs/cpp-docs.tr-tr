---
title: 'Nasıl yapılır: kaynakları derleme zamanında dahil | Microsoft Docs'
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
- compiling source code, including resources
- comments [C++], compiled files
- resources [Visual Studio], including at compile time
- projects [C++], including resources
- '#include directive'
- include directive (#include)
ms.assetid: 357e93c2-0a29-42f9-806f-882f688b8924
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 765d78ef5371015fdce3e505e7a2454c29c6c97e
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="how-to-include-resources-at-compile-time"></a>Nasıl Yapılır: Derleme Sırasında Kaynak Ekleme
Normalde kolay ve tüm kaynakların bir kaynak (.rc) komut dosyasında varsayılan düzenleme çalışmak uygun olur. Ancak, kaynakları diğer dosyalar geçerli projenize derleme zamanında bunları listeleyerek ekleyebileceğiniz **derleme zamanı yönergeleri** kutusunda [kaynağını içeren iletişim kutusunu](../windows/resource-includes-dialog-box.md).  
  
 Ana .rc dosyası dışında bir dosyada kaynakları yerleştirmek için birkaç nedeni vardır:  
  
-   .Rc dosyasını kaydettiğinizde, silinecek değil kaynak deyimleri açıklamaları eklemek için.  
  
     Kaynak düzenleyicileri .rc veya resource.h dosyaları doğrudan okuyamadı. Kaynak Derleyicisi bunları kaynak düzenleyicileri tarafından tüketilen .aps dosyalarına derler. Bu dosyayı bir derleme adımdır ve yalnızca simgesel verileri depolar. İşlem ile normal bir derleme gibi bilgileri (örneğin, Yorumlar) sembolik değil derleme işlemi sırasında göz ardı edilir. .Aps dosya .rc dosyasıyla out eşitlenmiş alır her .rc dosyasını yeniden oluşturur (kaydettiğinizde, örneğin, Kaynak Düzenleyici .rc dosyası ve resource.h dosyası geçersiz kılar). Kaynaklardaki değişiklikleri .rc dosyasında eklenen kalır ancak .rc dosyanın üzerine sonra açıklamaları her zaman kaybolur.  
  
-   Zaten geliştirilen ve test kaynakları eklemek ve daha fazla değişiklik gerekmez. (Dahil edilen ancak .rc uzantı olmayan herhangi bir dosya kaynak düzenleyicileri tarafından düzenlenebilir olmaz.)  
  
-   Birkaç farklı proje tarafından kullanılmakta olan veya kaynak kodu sürüm denetimi sistemi parçası olan ve böylece değişikliklerin tüm projeleri burada etkiler merkezi bir konumda bulunmalıdır kaynakları eklemek için.  
  
-   Özel bir biçimde olan kaynaklar (örneğin, RCDATA kaynakları) eklemek için. RCDATA kaynakları özel gereksinimleri olabilir. Örneğin, bir ifade nameID alanı için bir değer olarak kullanamaz. Bkz: [!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)] daha fazla bilgi için.  
  
 Bu koşulların herhangi biri karşılayan mevcut .rc dosyalarınızda bölümleri varsa, bölümler birinde yerleştirmelisiniz veya ayrı .rc dosyaları ve bunları kullanarak projesi dahil daha fazla [kaynağını içeren iletişim kutusunu](../windows/resource-includes-dialog-box.md). *Projectname*yeni bir proje \res alt dizininde oluşturulan .rc2 dosyası bu amaç için kullanılır.  
  
### <a name="to-include-resources-in-your-project-at-compile-time"></a>Kaynakları derleme zamanında projenize eklemek için  
  
1.  Kaynak betik dosyasını benzersiz bir dosya adı ile kaynakları yerleştirin. Kullanmayın *projectname*.rc, bu ana kaynak komut dosyası için kullanılan dosya adı olduğundan.  
  
2.  .Rc dosyaya sağ tıklayın (içinde [kaynak görünümü](../windows/resource-view-window.md)) ve **kaynağını içeren** kısayol menüsünden.  
  
3.  İçinde **derleme zamanı yönergeleri** kutusunda, eklemek [#include](../preprocessor/hash-include-directive-c-cpp.md) derleyici yönergesi geliştirme ortamında ana kaynak dosyasında yeni kaynak dosyası içerir.  
  
     Bu şekilde bulunan dosyalar kaynaklarında bir bölümü, yürütülebilir bir dosyanın derleme zamanında yapılır. Projenizin ana .rc dosyada çalışırken düzenleme veya değiştirilmesi için doğrudan kullanılamaz. Dahil edilen .rc dosyaları ayrı olarak açmanız gerekir. Dahil edilen ancak .rc uzantı olmayan herhangi bir dosya kaynak düzenleyicileri tarafından düzenlenebilir olmaz.  
  

  
 Gereksinimler  
  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak dosyaları](../windows/resource-files-visual-studio.md)   
 [Kaynak Düzenleyicileri](../windows/resource-editors.md)