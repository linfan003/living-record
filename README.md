# living-record

**数字永生里现在能公开的一层：判断必须引用记录。** 每条记录写明范围、出处和复核日期。过期、越界或互相矛盾的记录，不能被混成「这就是你的决定」。

English summary: a small protocol for a personal judgment record. An agent may use a record only when it can name the scope, the source, and the date. It does not imitate a person's voice, and it does not speak for them after they can no longer confirm a record.

This repository does **not** redefine [`SKILL.md`](https://agentskills.io). It specifies which personal records an agent may rely on. Session identity and file sharing live in the sibling project [session-canon](https://github.com/linfan003/session-canon).

## 这套协议解决什么

人反复问 AI 做判断时，AI 会积下这个人的情况。积得多，不等于判得准。旧偏好、另一个生活范围里的事、以及模型自己的推断，都会让判断偏掉。准，靠的是用得上的那几条记录，并且答的时候指得出来。

协议全文在 [spec/PROTOCOL.md](spec/PROTOCOL.md)（English: [spec/PROTOCOL.en.md](spec/PROTOCOL.en.md)）。

1. 没有引用，就不能说「这是按你的记录做的判断」。
2. 每条记录有一句话、一个范围、一个出处、记下的日期、复核日期。
3. 范围互相隔开。工作里的问题不读取健康范围，除非用户这一次明确说可以。
4. 出处只有三种：本人说过、本人文件、推断。推断不能压过本人说过的话。
5. 过了复核日期就停用。先问还成不成立，不默默继续用。
6. 同一范围内两条有效记录互相矛盾时，两条都摆出来，不取折中。
7. 一条记录一件事。密钥、账号和成套生活档案不写进记录。
8. 本协议不模仿这个人的声音，也不在他无法确认记录之后代替他说话。

## 目录

```
living-record/
├── spec/PROTOCOL.md           协议（中文）
├── spec/PROTOCOL.en.md        protocol (English)
├── spec/RELATED.md            相近项目与差别
├── skills/
│   ├── record-entry/          记下一条有出处的记录
│   ├── cite-judgment/         引用记录再做判断
│   └── review-stale/          找出过了复核日期的记录
├── templates/                 空记录
└── examples/weekday/          一份虚构的工作日记录
```

## 怎么用

1. 选一个只属于你的目录存放记录。它可以和 session-canon 的真源放在一起，也可以分开。不要把这个目录推进公开仓库。
2. 把 `templates/record.md` 复制成 `records/` 下的一个文件，填范围、出处和日期。
3. 把 `skills/` 放到 Agent 能读到的 skill 目录。
4. 让 Agent 做判断时说「按我的记录来」。它应先引用有效记录；没有可用记录时，直接说没有，而不是补一个像你的答案。

## 许可

Apache-2.0。见 [LICENSE](LICENSE)。
