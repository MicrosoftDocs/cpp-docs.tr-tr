---
title: C++ sınıflarında dllimport ve dllexport kullanma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- exporting classes [C++]
- declarations [C++], class
- exportable classes [C++]
- classes [C++], declaring
- classes [C++], exportable and inheritance
- inheritance [C++], exportable classes [C++]
- dllimport attribute [C++], classes
- declaring classes [C++]
- dllexport attribute [C++]
- dllexport attribute [C++], classes [C++]
ms.assetid: 8d7d1303-b9e9-47ca-96cc-67bf444a08a9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fe1454ee615f489190ec455adabcd4bdecb4e0f0
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39460826"
---
# <a name="using-dllimport-and-dllexport-in-c-classes"></a>C++ Sınıflarında dllimport ve dllexport Kullanma
## <a name="microsoft-specific"></a>Microsoft'a Özgü  
 C++ sınıflarını bildirebilirsiniz **dllimport** veya **dllexport** özniteliği. Bu formlar, sınıfın tamamı içe veya dışa aktarıldığını belirtir. Bu şekilde dışarı aktarılan sınıflar, dışarı aktarılabilir sınıflar olarak adlandırılır.  
  
 Aşağıdaki örnek dışarı aktarılabilen bir sınıfı tanımlar. Tüm üye işlevleri ve statik veriler dışarı aktarılır:  
  
```cpp 
#define DllExport   __declspec( dllexport )  
  
class DllExport C {  
   int i;  
   virtual int func( void ) { return 1; }  
};  
```  
  
 Bu açık kullanımına dikkat edin **dllimport** ve **dllexport** dışa aktarılabilir bir sınıfın üyelerinde öznitelikler kullanılamaz.  
  
##  <a name="_pluslang_using_dllimport_and_dllexport_in_c2b2bdllexportclasses"></a> dllexport sınıfları  
 Bir sınıfı bildirdiğinizde **dllexport**, tüm üye işlevleri ve statik veri üyeleri dışa aktarılır. Tür üyelerin tümünü aynı programda tanımları sağlamanız gerekir. Aksi halde bir bağlayıcı hatası meydana gelir. Bu kuralın tek istisnası, kendisi için açık tanımlar sağlamak zorunda olmadığınız saf sanal işlevler için geçerlidir. Ancak, soyut bir sınıf için yok edici her zaman temel sınıf için yok edici tarafından çağrıldığından, saf sanal yok ediciler her zaman bir tanım sağlamalıdır. Bu kuralların dışa aktarılamayan sınıflar için aynı olduğunu unutmayın.  
  
 Sınıf veya sınıf döndüren işlevleri, verileri dışarı aktarma, sınıfı aktardığınızdan emin olun.  
  
##  <a name="_pluslang_dllexport_classesdllexportclasses"></a> dllimport sınıfları  
 Bir sınıfı bildirdiğinizde **dllimport**, tüm üye işlevleri ve statik veri üyeleri içe aktarılır. Farklı **dllimport** ve **dllexport** nonclass türlerinde, aynı programda, bir tanımı statik veri üyeleri belirtilemez bir **dllimport** sınıfı tanımlı.  
  
##  <a name="_pluslang_using_dllimport_and_dllexport_in_c2b2binheritanceandexportableclasses"></a> Devralma ve dışa aktarılabilir sınıflar  
 Dışa aktarılabilir bir sınıfın tüm temel sınıfları dışa aktarılabilir olmalıdır. Aksi durumda, bir derleyici uyarısı oluşturulur. Ayrıca, aynı zamanda sınıf olan tüm erişilebilir üyeler dışa aktarılabilir olmalıdır. Bu kural izin veren bir **dllexport** devralınacak sınıfı bir **dllimport** sınıfı ve **dllimport** devralınacak sınıfı bir **dllexport** (ikinci önerilmez) sınıfı. Bir kural olarak, (C++ erişim kurallarına göre) DLL istemcisi için erişilebilir olan her şeyi dışarı aktarılabilir arabirimin bir parçası olmalıdır. Bu, satır içi işlevlerde başvurulan özel veri üyelerini içerir.  
  
##  <a name="_pluslang_using_dllimport_and_dllexport_in_c2b2bselectivememberimportexport"></a> Seçici üye içe/dışa aktarma  
 Üye işlevleri ve statik veriler bir sınıf içinde örtük olarak dış bağlantıya sahip olduğundan, bildirebilirsiniz **dllimport** veya **dllexport** sınıfın tamamı dışa sürece özniteliği. Sınıfın tamamı içe veya dışa açık üye işlevleri ve verileri olarak bildirimi, **dllimport** veya **dllexport** yasaktır. Sınıf tanımındaki statik veri üyesine bildirirseniz **dllexport**, bir tanımı yere (nonclass dış bağlantısıyla ile) aynı programın içinde gerçekleşmelidir.  
  
 Benzer şekilde, üye işlevleri ile bildirebilirsiniz **dllimport** veya **dllexport** öznitelikleri. Bu durumda, sağlamanız gereken bir **dllexport** aynı programda bir yere tanımı.  
  
 Faydalı Seçici üyelerin içe ve dışa aktarma ile ilgili birkaç önemli noktalara dikkat edin:  
  
-   Seçici üye içe/dışa aktarma daha kısıtlayıcıdır dışarı aktarılan sınıf arabirimi sürümü sağlamak için en iyi şekilde kullanılır. diğer bir deyişle, bir dil daha az ortak ve özel özellikleri sunan bir DLL tasarlayabilmek için Aksi takdirde çalıştırmasına olanak tanır. De dışa aktarılabilir arabirimde hassas ayarlamaları yapmak için kullanışlıdır: tanımına göre istemcinin bazı özel verilere erişemediğini biliyorsanız, sınıfın tamamı dışa aktarmanız gerekir.  
  
-   Bir sanal işlevi bir sınıf dışarı aktarırsanız, bunların tümünü Dışarı Aktar veya en azından istemcinin doğrudan kullanabileceği sürümleri sağlar.  
  
-   Bir sınıf sanal işlevler ile Seçici üye içe/dışa aktarma kullanmakta olduğunuz varsa, işlevlerin dışa aktarılabilir arabirimde olması gerekir veya (istemci tarafından görünür) satır içi tanımlanmış.  
  
-   Üye olarak tanımlarsanız **dllexport** ancak bunu sınıf tanımına eklemeyin, bir derleyici hatası oluşturulur. Sınıf üstbilgisinde üye tanımlamanız gerekir.  
  
-   Ancak sınıf üyelerinin tanımına **dllimport** veya **dllexport** olan izin, sınıf tanımında belirtilen arabirim geçersiz kılınamaz.  
  
-   Üye işlevini, bildirdiğiniz sınıf tanımının gövdesi haricinde bir yerde tanımlarsanız, işlevin olarak tanımlanırsa, bir uyarı oluşturulduğu **dllexport** veya **dllimport** (Bu tanımı farklıdır sınıfı bildiriminde belirtilen).  
  
**END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [dllexport, dllimport](../cpp/dllexport-dllimport.md)