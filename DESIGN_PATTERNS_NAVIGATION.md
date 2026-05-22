# 设计模式分类导航

本项目包含了大量设计模式的Java实现，以下按照经典GOF 23种设计模式进行分类导航，同时列出其他常用的非GOF设计模式。

---

## GOF 23种经典设计模式

### 创建型模式（Creational Patterns）
用于处理对象创建逻辑，将对象的创建与使用分离：
- [抽象工厂模式（Abstract Factory）](./abstract-factory/)：提供创建一系列相关或依赖对象的接口，无需指定具体类
- [建造者模式（Builder）](./builder/)：将复杂对象的构建与其表示分离，同样的构建过程可以创建不同的表示
- [工厂方法模式（Factory Method）](./factory-method/)：定义创建对象的接口，让子类决定实例化哪个类，将类的实例化延迟到子类
- [原型模式（Prototype）](./prototype/)：用原型实例指定创建对象的种类，通过拷贝原型创建新对象
- [单例模式（Singleton）](./singleton/)：确保一个类只有一个实例，并提供全局访问点

### 结构型模式（Structural Patterns）
处理类或对象的组合关系，通过组合得到新的功能：
- [适配器模式（Adapter）](./adapter/)：将一个类的接口转换成客户希望的另一个接口，解决接口不兼容问题
- [桥接模式（Bridge）](./bridge/)：将抽象部分与实现部分分离，使它们都可以独立变化
- [组合模式（Composite）](./composite/)：将对象组合成树形结构以表示"部分-整体"层次关系，用户对单个对象和组合对象的使用具有一致性
- [装饰器模式（Decorator）](./decorator/)：动态给对象添加额外职责，比继承更灵活
- [外观模式（Facade）](./facade/)：为子系统中的一组接口提供统一高层接口，简化子系统使用
- [享元模式（Flyweight）](./flyweight/)：运用共享技术有效支持大量细粒度对象，减少内存占用
- [代理模式（Proxy）](./proxy/)：为其他对象提供代理以控制对这个对象的访问

### 行为型模式（Behavioral Patterns）
处理对象之间的交互和职责分配，描述算法和对象间的协作：
- [责任链模式（Chain of Responsibility）](./chain-of-responsibility/)：使多个对象都有机会处理请求，避免请求发送者和接收者耦合，将这些对象连成一条链，沿着链传递请求
- [命令模式（Command）](./command/)：将请求封装为对象，使你可用不同的请求对客户进行参数化，支持可撤销操作
- [解释器模式（Interpreter）](./interpreter/)：给定一个语言，定义它的文法表示，并定义解释器使用该表示来解释语言中的句子
- [迭代器模式（Iterator）](./iterator/)：提供一种方法顺序访问聚合对象中各个元素，而不暴露对象的内部表示
- [中介者模式（Mediator）](./mediator/)：用中介对象封装一系列对象交互，使各对象不需要显式相互引用，耦合松散，独立改变交互
- [备忘录模式（Memento）](./memento/)：在不破坏封装性的前提下，捕获一个对象的内部状态，并在对象之外保存这个状态，以便后续恢复
- [观察者模式（Observer）](./observer/)：定义对象间一对多依赖关系，当一个对象状态变化时，所有依赖它的对象收到通知并自动更新
- [状态模式（State）](./state/)：允许对象在内部状态改变时改变它的行为，对象看起来好像修改了它的类
- [策略模式（Strategy）](./strategy/)：定义一系列算法，把它们一个个封装起来，使它们可以互相替换，算法独立于使用它的客户变化
- [模板方法模式（Template Method）](./template-method/)：定义一个操作中的算法骨架，将步骤延迟到子类中，子类不改变算法结构即可重定义算法特定步骤
- [访问者模式（Visitor）](./visitor/)：表示一个作用于某对象结构中的各元素的操作，你可以在不改变各元素类的前提下定义作用于这些元素的新操作

---

## 其他常用设计模式（非GOF23种）
### 并发模式
- [主动对象模式（Active Object）](./active-object/)：将方法调用与执行解耦，每个对象维护独立的消息队列和执行线程，支持异步处理请求，提高并发响应性
- [消息队列模式（Event Queue）](./event-queue/)：使用缓冲区存储事件消息，解耦消息生产者和消费者，支持异步处理、流量削峰和事件广播
- [生产者消费者模式（Producer Consumer）](./producer-consumer/)：通过缓冲区隔离生产任务和消费任务，平衡两者处理速率差异，支持多生产者多消费者并发工作
- [线程池模式（Thread Pool Executor）](./thread-pool-executor/)：维护可复用的线程集合执行任务，避免频繁创建销毁线程的开销，控制并发线程数量，提高系统资源利用率
- [反应器模式（Reactor）](./reactor/)：单/少量线程同步等待IO事件，分发给对应处理器处理，实现高并发非阻塞IO，适合网络服务场景
- [半同步半异步模式（Half Sync Half Async）](./half-sync-half-async/)：分离异步请求接收和同步任务处理，既保证高并发吞吐量，又简化同步业务逻辑开发
- [监听器模式（Guarded Suspension）](./guarded-suspension/)：线程在等待特定条件满足时挂起，条件满足后自动唤醒继续执行，避免CPU空转浪费资源
- [互斥模式（Monitor）](./monitor/)：封装共享资源和临界区操作，保证同一时间只有一个线程访问共享资源，避免多线程竞争导致的数据不一致

### 架构模式
- [分层架构（Layered Architecture）](./layered-architecture/)：将应用按职责划分为垂直层次，每层只依赖下层，实现关注点分离，提高代码可维护性和可复用性
- [六边形架构（Hexagonal Architecture）](./hexagonal-architecture/)：核心业务逻辑位于中心，通过抽象端口与外部系统交互，使用适配器适配不同外部实现，保证核心逻辑独立于外部技术
- [整洁架构（Clean Architecture）](./clean-architecture/)：按依赖规则将系统分为多层，圆心是核心业务逻辑，外层是框架和IO实现，依赖只能从外向内，保证业务逻辑不受外部技术变化影响
- [微服务聚合模式（Microservices Aggregrator）](./microservices-aggregrator/)：聚合多个微服务的响应结果统一返回给客户端，减少客户端多次调用的网络开销，简化客户端逻辑
- [微服务API网关模式（Microservices API Gateway）](./microservices-api-gateway/)：作为微服务系统统一入口，处理请求路由、认证、限流、监控等横切关注点，对外提供统一API接口
- [事件驱动架构（Event Driven Architecture）](./event-driven-architecture/)：以事件作为核心交互媒介，各组件通过事件异步通信，实现松耦合、高可扩展的系统架构
- [MVC模式（Model View Controller）](./model-view-controller/)：将应用分为模型（数据）、视图（展示）、控制器（逻辑）三层，分离数据展示和业务逻辑，提高代码可维护性
- [MVVM模式（Model View ViewModel）](./model-view-viewmodel/)：将视图与模型通过ViewModel层绑定，实现数据和视图的自动同步，简化前端界面开发
- [MVP模式（Model View Presenter）](./model-view-presenter/)：通过Presenter层作为视图和模型的中介，完全隔离视图和模型，便于单元测试和逻辑复用
- [MVI模式（Model View Intent）](./model-view-intent/)：以单向数据流为核心，所有用户操作以Intent形式发送，更新单一状态源驱动视图变化，保证状态一致性
- [前端控制器模式（Front Controller）](./front-controller/)：为所有请求提供统一入口处理，集中处理认证、路由、日志等公共逻辑，简化请求处理流程

### 企业应用模式
- [数据访问对象（Data Access Object）](./data-access-object/)：抽象数据持久化操作，封装数据库访问细节，分离业务逻辑和数据访问逻辑，支持不同存储实现切换
- [数据传输对象（Data Transfer Object）](./data-transfer-object/)：聚合多个数据到单个对象，减少跨层或网络调用次数，优化数据传输效率，避免暴露内部数据结构
- [仓储模式（Repository）](./repository/)：抽象领域对象的集合操作，封装数据存储和查询逻辑，提供领域层与数据映射层的中介，统一数据访问入口
- [工作单元模式（Unit of Work）](./unit-of-work/)：维护多个业务操作的事务一致性，追踪对象状态变化，统一提交或回滚所有相关操作，保证数据一致性
- [服务定位器模式（Service Locator）](./service-locator/)：提供全局服务注册和查找机制，封装服务创建和依赖解析逻辑，解耦服务使用者和提供者的实现依赖
- [服务层模式（Service Layer）](./service-layer/)：封装业务逻辑，为上层提供统一的业务服务接口，协调多个领域对象完成复杂业务操作，隔离表现层和领域层
- [业务代表模式（Business Delegate）](./business-delegate/)：封装对业务服务的访问细节，隐藏服务定位和远程调用逻辑，降低表现层和业务服务层的耦合度
- [组合实体模式（Composite Entity）](./composite-entity/)：将一组相关的领域对象组合成单一实体，简化粗粒度对象的管理和持久化，减少远程调用次数
- [值对象模式（Value Object）](./value-object/)：表示不可变的、仅由属性值定义的对象，没有唯一标识，用于封装值集合，提高代码可读性和安全性
- [规约模式（Specification）](./specification/)：将业务规则封装为独立的规约对象，支持规则组合和复用，实现业务规则与业务逻辑的分离
- [乐观离线锁模式（Optimistic Offline Lock）](./optimistic-offline-lock/)：通过版本号机制检测并发修改冲突，避免长时间持有数据库锁，提高离线编辑场景的并发性能

### 云原生/分布式模式
- [断路器模式（Circuit Breaker）](./circuit-breaker/)：监控服务调用失败率，失败达到阈值时快速熔断，避免级联故障，保护系统稳定性，提供降级和恢复机制
- [舱壁模式（Bulkhead，在resilience4j相关实现中）](./retry/)：将系统资源按功能隔离划分，避免某一功能故障耗尽所有资源，提高系统容错性和可用性
- [重试模式（Retry）](./retry/)：对临时故障的服务调用进行自动重试，提高系统容错能力，减少瞬时故障导致的调用失败
- [限流模式（Rate Limiting Pattern）](./rate-limiting-pattern/)：限制请求访问速率，保护系统不被突发流量冲垮，保证服务在承载能力范围内稳定运行
- [服务发现模式（Service Registry）](./registry/)：动态维护服务实例的注册信息，服务消费者通过注册中心查找可用服务实例，支持服务动态扩缩容
- [Saga模式（Saga）](./saga/)：将分布式事务拆分为多个本地事务，通过补偿机制保证分布式事务的最终一致性，避免长事务锁定资源
- [背压模式（Backpressure）](./backpressure/)：在数据处理链路中，下游控制上游的数据发送速率，避免下游处理能力不足导致的系统过载
- [消息发布订阅模式（Publish Subscribe）](./publish-subscribe/)：消息生产者将消息发布到主题，所有订阅该主题的消费者都能收到消息，实现一对多的异步通信
- [毒药丸模式（Poison Pill）](./poison-pill/)：通过发送特殊终止消息，优雅关闭消息处理链路，保证正在处理的消息能正常完成，避免强制关闭导致的数据丢失
- [大使模式（Ambassador）](./ambassador/)：为服务实例提供本地代理，处理服务间通信的横切关注点，如监控、日志、限流、重试等，简化服务开发
- [防腐层模式（Anti Corruption Layer）](./anti-corruption-layer/)：在不同系统或新旧系统之间建立转换层，隔离外部系统的设计和实现差异，保护内部系统的领域模型不受外部影响
- [分片模式（Sharding）](./sharding/)：将大规模数据按规则拆分为多个分片存储在不同节点，突破单节点存储和性能瓶颈，支持大规模数据的水平扩展

### 性能优化模式
- [缓存模式（Caching）](./caching/)：将高频访问的数据存储在高速存储介质中，减少重复计算或数据库访问，大幅提高系统响应速度和吞吐量
- [懒加载模式（Lazy Loading）](./lazy-loading/)：延迟对象或资源的加载时机，直到真正使用时才加载，减少系统启动时间和内存占用
- [对象池模式（Object Pool）](./object-pool/)：维护可复用的对象集合，避免频繁创建销毁对象的开销，适合创建成本高、使用频繁的对象场景
- [脏标记模式（Dirty Flag）](./dirty-flag/)：标记已修改的数据，避免每次都全量更新，只在需要时批量更新已修改部分，提高数据更新效率
- [数据局部性模式（Data Locality）](./data-locality/)：将相关数据存储在相邻位置，提高缓存命中率，减少IO访问延迟，提升数据处理性能
- [虚拟代理模式（Virtual Proxy）](./virtual-proxy/)：用轻量级代理对象代替重量级真实对象，延迟真实对象的加载和创建，节省内存和启动时间

### 其他模式
- [回调模式（Callback）](./callback/)：将后续处理逻辑作为参数传递给异步方法，异步操作完成后自动调用回调逻辑，简化异步编程
- [空对象模式（Null Object）](./null-object/)：用特殊的空对象代替null值，避免空指针异常，统一空情况的处理逻辑，简化判空代码
- [特殊案例模式（Special Case）](./special-case/)：将特殊情况的处理逻辑封装为独立对象，避免大量条件判断语句，提高代码可读性和可维护性
- [参数对象模式（Parameter Object）](./parameter-object/)：将多个相关参数封装为单一对象，简化方法签名，避免参数过多导致的调用错误，提高代码可读性
- [步骤构建器模式（Step Builder）](./step-builder/)：将复杂对象的构建过程拆分为多个强制步骤，通过分步引导保证必填参数都被设置，避免构造对象时遗漏参数
- [流利接口模式（Fluent Interface）](./fluent-interface/)：通过方法链式调用实现流畅的API设计，提高代码可读性，更接近自然语言表达
- [依赖注入模式（Dependency Injection）](./dependency-injection/)：由外部容器负责注入对象的依赖，解耦对象创建和使用逻辑，提高代码可测试性和可维护性
- [幂等消费者模式（Idempotent Consumer）](./microservices-idempotent-consumer/)：保证消息消费逻辑的幂等性，即使消息被重复消费也不会产生错误结果，提高分布式系统的可靠性
- [Strangler模式（Strangler）](./strangler/)：逐步替换老旧系统的功能，新旧系统并行运行，逐步将流量迁移到新系统，最终完全替换旧系统，降低系统重构风险
- [交易脚本模式（Transaction Script）](./transaction-script/)：将每个业务用例封装为单个事务脚本，适合简单业务场景，开发效率高，逻辑直接易懂
- [表模块模式（Table Module）](./table-module/)：每个数据库表对应一个业务处理类，封装该表的所有业务操作，适合事务脚本和表驱动的业务场景
- [标识映射模式（Identity Map）](./identity-map/)：维护已加载对象的映射表，保证同一标识的对象只加载一次，避免重复查询数据库，提高性能和数据一致性
- [数据映射模式（Data Mapper）](./data-mapper/)：在对象和数据库之间建立双向映射，分离对象模型和数据模型，解耦业务逻辑和数据存储结构
