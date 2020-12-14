---
description: 'Daha fazla bilgi edinin: kilitleme davranışına açıklama ekleme'
title: Kilitlenme Davranışını Yorumlama
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- _Releases_nonreentrant_lock_
- _Lock_kind_mutex_
- _Lock_kind_critical_section_
- _Acquires_lock_
- _Releases_lock_
- _Has_lock_kind_
- _Releases_exclusive_lock_
- _Post_same_lock_
- _Requires_exclusive_lock_held_
- _Requires_shared_lock_held_
- _Lock_kind_semaphore_
- _Requires_lock_held_
- _Acquires_exclusive_lock_
- _Create_lock_level_
- _Acquires_nonreentrant_lock_
- _Releases_shared_lock_
- _Has_lock_level_
- _Lock_kind_spin_lock_
- _Requires_lock_not_held_
- _Acquires_shared_lock_
- _Requires_no_locks_held_
- _Lock_level_order_
- _Lock_kind_event_
ms.assetid: 07769c25-9b97-4ab7-b175-d1c450308d7a
ms.openlocfilehash: c26f33b9e2464f91786a6607cea9c3520b971824
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97279630"
---
# <a name="annotating-locking-behavior"></a>Kilitlenme Davranışını Yorumlama

Çok iş parçacıklı programınızda eşzamanlılık hatalarından kaçınmak için, her zaman uygun bir tane disiplin ve SAL ek açıklamalarını kullanın.

Eşzamanlılık hataları, belirleyici olmayan bir şekilde yeniden oluşturmak, tanılamak ve hata ayıklamak için çok zor. İş parçacığı araya ekleme hakkında bilgi, en iyi şekilde zordur ve birkaç iş parçacığına sahip bir kod gövdesi tasarlarken pratik hale gelir. Bu nedenle, çok iş parçacıklı programlarınızda bir kilitleme disiplini izlemek iyi bir uygulamadır. Örneğin, birden çok kilit edinirken bir kilit sırasını uygulamaya getirmek, kilitlenmeleri önlemeye yardımcı olur ve paylaşılan bir kaynağa erişmeden önce doğru koruma kilitlenmesinin, yarış koşullarından kaçınmanıza yardımcı olur.

Ne yazık ki, ortaya çıkacak basit kilitleme kurallarının uygulamada izlenmesi çok zor olabilir. Bugünün programlama dillerinde ve derleyicilerinin temel sınırlaması, eşzamanlılık gereksinimlerinin belirtimini ve analizini doğrudan desteklemeleridir. Programcıların kilitleri nasıl kullandıkları hakkında bilgi almak için resmi olmayan kod açıklamalarına güvenmeleri gerekir.

Eşzamanlılık SAL ek açıklamaları, kilitleme yan etkileri, kilitleme sorumluluğu, veri koruyucuları, kilit sırası hiyerarşisi ve diğer beklenen kilitleme davranışını belirtmenize yardımcı olacak şekilde tasarlanmıştır. Örtülü kuralları açık hale getirerek SAL eşzamanlılık ek açıklamaları, kodunuzun kilitleme kurallarını nasıl kullandığını belgelemeniz için tutarlı bir yol sağlar. Eşzamanlılık ek açıklamaları Ayrıca, kod analizi araçlarının yarış koşullarını, kilitlenmeleri, eşleşmeyen eşitleme işlemlerini ve diğer hafif eşzamanlılık hatalarını bulma yeteneğini geliştirir.

## <a name="general-guidelines"></a>Genel Yönergeler

Ek açıklamaları kullanarak, uygulamalar (Callet 'ler) ve istemcileri (çağıranlar) arasında işlev tanımları tarafından kapsanan sözleşmeleri ve daha fazla analizi daha da iyileştirebilecek programın diğer özelliklerini belirtebilir.

SAL, birçok farklı kilit temel türünü destekler; Örneğin, kritik bölümler, zaman uyumu sağlayıcılar, döndürme kilitleri ve diğer kaynak nesneleri. Birçok eşzamanlılık ek açıklaması, bir kilit ifadesini parametre olarak alır. Kurala göre, bir kilit, temeldeki kilit nesnesinin yol ifadesiyle gösterilir.

Göz önünde bulundurmanız gereken bazı iş parçacığı sahiplik kuralları:

- Döndürme kilitleri, açık iş parçacığı sahipliğini içeren sayılmayan kilitlerdir.

- Birbirini kapsamalı ve kritik bölümler, açık iş parçacığı sahipliğini içeren kilitler olarak sayılır.

- Semaforlar ve olaylar, açık iş parçacığı sahipliğini olmayan kilitler olarak sayılır.

## <a name="locking-annotations"></a>Ek açıklamaları kilitleme

Aşağıdaki tabloda kilitleme ek açıklamaları listelenmektedir.

|Ek Açıklama|Açıklama|
|----------------|-----------------|
|`_Acquires_exclusive_lock_(expr)`|Bir işlevi öğretme ve işlevin,, tarafından adlandırılan kilit nesnesinin dışlamalı kilit sayısıyla bir şekilde artırdığını gösterir `expr` .|
|`_Acquires_lock_(expr)`|Bir işlevi daha fazla açıklama olarak gösterir ve işlevin, tarafından adlandırılan kilit nesnesinin kilit sayısıyla bir kilit sayısına göre artırılmasını sağlar `expr` .|
|`_Acquires_nonreentrant_lock_(expr)`|Tarafından adlandırılan kilit `expr` alındı.  Kilit zaten tutuluyorsa bir hata bildirilir.|
|`_Acquires_shared_lock_(expr)`|Bir işlevi daha fazla açıklama olarak gösterir ve işlevin, tarafından adlandırılan kilit nesnesinin paylaşılan kilit sayısıyla bir tane artar `expr` .|
|`_Create_lock_level_(name)`|Simgeler `name` ve ek açıklamalarda kullanılabilmesi için simgeyi bir kilit düzeyi olarak bildiren bir ifade `_Has_Lock_level_` `_Lock_level_order_` .|
|`_Has_lock_kind_(kind)`|Bir kaynak nesnesinin tür bilgilerini iyileştirmek için herhangi bir nesneye Açıklama Ekle. Bazen, farklı türlerde kaynaklar için ortak bir tür kullanılır ve aşırı yüklenmiş tür çeşitli kaynaklar arasındaki anlam gereksinimlerini ayırt etmek için yeterli değildir. Önceden tanımlanmış parametrelerin listesi aşağıdadır `kind` :<br /><br /> `_Lock_kind_mutex_`<br /> Zaman uyumu sağlayıcılar için kilit türü KIMLIĞI.<br /><br /> `_Lock_kind_event_`<br /> Olaylar için kilit türü KIMLIĞI.<br /><br /> `_Lock_kind_semaphore_`<br /> Semaforlar için kilit türü KIMLIĞI.<br /><br /> `_Lock_kind_spin_lock_`<br /> Döndürme kilitleri için kilit türü KIMLIĞI.<br /><br /> `_Lock_kind_critical_section_`<br /> Kritik bölümler için kilit türü KIMLIĞI.|
|`_Has_lock_level_(name)`|Bir kilit nesnesine bir açıklama koyun ve bunun kilit düzeyini verir `name` .|
|`_Lock_level_order_(name1, name2)`|Ve arasında kilit sıralaması sağlayan bir ifade `name1` `name2` .  Düzeyi olan kilitler, `name1` düzeyi olan kilitlerin önüne alınmalıdır `name2` .|
|`_Post_same_lock_(expr1, expr2)`|Bir işlevi bir işleve açıklama ve gönderi durumunda iki kilit olduğunu `expr1` ve `expr2` aynı kilit nesnesi gibi değerlendirildiğini gösterir.|
|`_Releases_exclusive_lock_(expr)`|Bir işlevi daha fazla açıklama olarak gösterir ve işlevin, tarafından adlandırılan kilit nesnesinin dışlamalı kilit sayısına göre ne kadar azaltır `expr` .|
|`_Releases_lock_(expr)`|Bir işlevi daha fazla açıklama olarak gösterir ve işlevin, tarafından adlandırılan kilit nesnesinin kilit sayısı ile bir kilit sayısına göre azaltır `expr` .|
|`_Releases_nonreentrant_lock_(expr)`|Tarafından adlandırılan kilit `expr` serbest bırakılır. Kilit Şu anda tutulmadığında bir hata bildirilir.|
|`_Releases_shared_lock_(expr)`|Bir işlevi daha fazla açıklama olarak gösterir ve işlevin, tarafından adlandırılan kilit nesnesinin paylaşılan kilit sayısına göre ne kadar azaltır `expr` .|
|`_Requires_lock_held_(expr)`|Bir işlevi inceleyin ve ön durumunda tarafından adlandırılan nesnenin kilit sayısının `expr` en az bir olduğunu gösterir.|
|`_Requires_lock_not_held_(expr)`|Bir işlevi inceleyin ve ön durum ' da tarafından adlandırılan nesnenin kilit sayısının sıfır olduğunu gösterir `expr` .|
|`_Requires_no_locks_held_`|Bir işlevi inceleyin ve denetleyici tarafından bilinen tüm kilitlerin kilit sayısının sıfır olduğunu gösterir.|
|`_Requires_shared_lock_held_(expr)`|Bir işlevi inceleyin ve ön durumunda tarafından adlandırılan nesnenin paylaşılan kilit sayısının `expr` en az bir olduğunu gösterir.|
|`_Requires_exclusive_lock_held_(expr)`|Bir işlevi inceleyin ve ön durumunda tarafından adlandırılan nesnenin özel kilit sayısının `expr` en az bir olduğunu gösterir.|

## <a name="sal-intrinsics-for-unexposed-locking-objects"></a>Açığa çıkarmayan kilitleme nesneleri Için SAL Iç öğeler

Belirli kilit nesneleri ilişkili kilitleme işlevlerinin uygulanmasıyla gösterilmez.  Aşağıdaki tabloda, bu görünmeyen kilit nesnelerinde çalışan işlevlerde ek açıklamaları etkinleştiren açık iç değişkenler listelenmektedir.

|Ek Açıklama|Açıklama|
|----------------|-----------------|
|`_Global_cancel_spin_lock_`|İptal döndürme kilidini açıklar.|
|`_Global_critical_region_`|Kritik bölgeyi açıklar.|
|`_Global_interlock_`|Birbirine kenetlenmiş işlemleri açıklar.|
|`_Global_priority_region_`|Öncelik bölgesini açıklar.|

## <a name="shared-data-access-annotations"></a>Paylaşılan veri erişimi ek açıklamaları

Aşağıdaki tabloda, paylaşılan veri erişimi için ek açıklamalar listelenmektedir.

|Ek Açıklama|Açıklama|
|----------------|-----------------|
|`_Guarded_by_(expr)`|Bir değişkene açıklama koyun ve değişkene her erişildiğinde, tarafından adlandırılan kilit nesnesinin kilit sayısının `expr` en az bir olduğunu gösterir.|
|`_Interlocked_`|Bir değişkene açıklama koyun ve eşdeğerdir `_Guarded_by_(_Global_interlock_)` .|
|`_Interlocked_operand_`|Açıklamalı işlev parametresi, çeşitli birbirine kilitli işlevlerden birinin hedef işlenendir.  Bu işlenenler özel ek özelliklere sahip olmalıdır.|
|`_Write_guarded_by_(expr)`|Bir değişkene açıklama koyun ve değişken değiştirildiğinde, tarafından adlandırılan kilit nesnesinin kilit sayısının `expr` en az bir olduğunu gösterir.|

## <a name="smart-lock-and-raii-annotations"></a>Akıllı Kilit ve OYıı ek açıklamaları

Akıllı kilitler genellikle yerel kilitleri sarın ve ömrünü yönetir. Aşağıdaki tabloda, semantik desteğiyle akıllı kilitler ve SEıı kodlama desenleri ile kullanılabilen ek açıklamalar listelenmektedir `move` .

|Ek Açıklama|Açıklama|
|----------------|-----------------|
|`_Analysis_assume_smart_lock_acquired_`|Çözümleyiciye bir akıllı kilit elde edilen olduğunu varsaymasını söyler. Bu ek açıklama, parametresi olarak bir başvuru kilit türü bekliyor.|
|`_Analysis_assume_smart_lock_released_`|Çözümleyiciye, akıllı bir kilidin bırakıldığını varsaymasını söyler. Bu ek açıklama, parametresi olarak bir başvuru kilit türü bekliyor.|
|`_Moves_lock_(target, source)`|`move constructor`Nesnesinden kilit durumunu aktaran işlemi açıklar `source` `target` . , `target` Yeni oluşturulmuş bir nesne olarak değerlendirilir, bu nedenle önce sahip olduğu tüm durum kaybedilir ve durum tarafından değiştirilmez `source` . `source`Ayrıca, kilit sayısı veya diğer ad hedefi olmayan temiz bir duruma sıfırlanır, ancak bu, işaret eden diğer adlar değişmeden kalır.|
|`_Replaces_lock_(target, source)`|`move assignment operator`Durumu kaynaktan aktarmadan önce hedef kilidinin serbest bırakıldığı semantiğini açıklar. Bu, önünde bir birleşimi olarak kabul edilebilir `_Moves_lock_(target, source)` `_Releases_lock_(target)` .|
|`_Swaps_locks_(left, right)`|, `swap` Nesnelerin olduğunu varsayan `left` ve `right` bunların durumunu değiş tokuş eden standart davranışı açıklar. Değiştirilen durum, varsa kilit sayısını ve diğer ad hedefini içerir. Ve nesnelerine işaret eden diğer `left` adlar `right` değişmeden kalır.|
|`_Detaches_lock_(detached, lock)`|Bir kilit sarmalayıcı türünün içerdiği kaynakla ilişkilendirmesini geri almasına izin verdiği bir senaryoyu açıklar. Bu `std::unique_ptr` , iç işaretçiyle çalışma şekline benzerdir: programcıların işaretçiyi ayıklamasına ve akıllı işaretçi kapsayıcısını temiz bir durumda bırakmasını sağlar. Benzer mantık tarafından desteklenir `std::unique_lock` ve özel kilit sarmalayıcılarını kullanabilirsiniz. Ayrılmış kilit, kendi diğer adlarını korurken, bu nesnenin durumunu (varsa kilit sayısı ve diğer ad hedefi) korur. Kilit sayıları üzerinde hiçbir işlem yoktur (serbest bırakma ve alma). Bu ek açıklama `_Moves_lock_` , ayrılmış bağımsız değişkenin yerine olması dışında tam olarak davranır **`return`** **`this`** .|

## <a name="see-also"></a>Ayrıca bkz.

- [C/C++ Kod Hatalarını Azaltmak için SAL Ek Açıklamalarını Kullanma](../code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects.md)
- [SAL'ı Anlama](../code-quality/understanding-sal.md)
- [İşlev Parametrelerini ve Dönüş Değerlerini Açıklama](../code-quality/annotating-function-parameters-and-return-values.md)
- [İşlev Davranışını Yorumlama](../code-quality/annotating-function-behavior.md)
- [Yapıları ve Sınıfları Yorumlama](../code-quality/annotating-structs-and-classes.md)
- [Açıklamanın Ne Zaman ve Nereye Uygulanacağını Belirtme](../code-quality/specifying-when-and-where-an-annotation-applies.md)
- [İç Işlevler](../code-quality/intrinsic-functions.md)
- [En İyi Yöntemler ve Örnekler](../code-quality/best-practices-and-examples-sal.md)
