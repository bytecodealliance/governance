# How to Create and Kickoff a Special Interest Group (SIG)

## Proposing a SIG

As explained in the Bytecode Alliance [Technical Steering Committee charter](https://github.com/bytecodealliance/governance/blob/main/TSC/charter.md#creating-an-interest-group), any member of the Bytecode Alliance can propose the creation of an Interest Group. 
- [ ] Write a proposal to create the SIG, clearly identifing its scope and goals, and list the member(s) supporting its creation.  It is helpful to also have the proposal suggest willing Chairpersons for the SIG. 
- [ ] Submit the proposal as a pull request to the `SIGs` directory of [the `governance` repository of the Bytecode Allicance GitHub organization](https://github.com/bytecodealliance/governance/tree/main/SIGs) with a request for members to comment to be added as a supporting member to the proposal. TSC has the approval authority for the SIG. For an example, see the [SIG-docs pull request](https://github.com/bytecodealliance/governance/pull/45).
- [ ] The TSC will consider the proposal and make a decision in a reasonable timeframe. It may adopt the proposal as made, but it can also modify the proposal if it believes it necessary. If approved the TSC will formally appoint one or more Chairs, who should follow the steps below to establish the SIG. 

## Establishing a SIG

Bytecode Alliance SIGs operate transparently and in full public view, open to participation by all. Approved SIGs therefore require a variety of resources to support their operation. For help with any of these contact David Bryant, Bytecode Alliance Executive Director, at david@bytecodealliance.org

### On GitHub
- [ ] **Governance** Create a subfolder for the new SIG in the SIGs folder of the Bytecode Alliance [governance](https://github.com/bytecodealliance/governance/tree/main/SIGs) repository, making its existence and purpose officially public. 
    - [ ] Add the approved proposal for the SIG to its subfolder, making sure the stated scope, goals, and members are up to date.
    - [ ] Update the README in the overall SIGs subfolder to include the new SIG with its Chair(s).
- [ ] **Meetings** Create a subfolder for the new SIG in the Bytecode Alliance [`meetings`](https://github.com/bytecodealliance/meetings) repository, giving it a place to share important meeting info as well as gather meeting agenda and minutes.  This gives the SIG Chairs access to create and update all the SIGs meeting information in the `meetings` repo.
    - [ ] Create a new GitHub [team](https://github.com/orgs/bytecodealliance/teams) for the approved SIG Chairs, as a subteam of the existing `sig-chairs` GitHub team, and give that new team access to the SIGs subfolder in the `meetings` repository (via the `CODEOWNERS` file in the repo).
    - [ ] Add a README to the SIG's subfolder summarizing general information about attending SIG meetings.
    - [ ] Update the README in the [`meetings`](https://github.com/bytecodealliance/meetings) repo to include the new SIG and identify the SIG Chairs
    - [ ] Add meeting agegnda and notes to the subfolder as meetings are planned and occur, typically organized by year.


### Communications
- [ ] Ensure SIG Chairs are added to the [`sig-admin`](https://groups.google.com/u/1/a/bytecodealliance.org/g/sig-admin) Google Group to get admin information and access, such as in organizing Zoom meetings, access meeting recordings, update the Bytecode Alliance public calendar, etc.
- [ ] Create a Google Group for the SIG within the Bytecode Alliance Google Workspace, allowing easy communication and sharing of materials among SIG members. Make sure group permissions allow anyone on the web to ask to join.
- [ ] Create a  channel for the SIG on the Bytecode Alliance [`Zulip server`](https://bytecodealliance.zulipchat.com)
- [ ] Add SIG meetings to the Bytecode Alliance [public calendar](https://calendar.google.com/calendar/embed?src=events%40bytecodealliance.org&ctz=America%2FLos_Angeles). Include important details on joining the meeting or a link to where those details may be found.
- [ ] Announce the new SIG on Zulip in `#general`
- [ ] Add SIG chairs to the Bytecode Alliance 1Password Team account so they can access:
    - SIG Admin Zoom credentials to manage video meetings and meeting recordings
    - YouTube credentials to upload videos
    - Public Events calendar to schedule and maintain SIG meetings

## Running SIG Meetings

In addition to the `meetings` repository mentioned above for sharing meeting agenda and minutes, the Bytecode Alliance maintains a Zoom account to enable video meeting support and recording for all its SIGs. Meeting recordings are shared using the Bytecode Alliance's YouTube account.

The following are minimum requirements of running a SIG:

- All meetings must be public.  The Zoom link need not be publicly available, to avoid Zoom bombing, but should be shared with anyone who requests it.
- Attendance and notes should be taken at all meetings
- It is recommended, but not required, that meetings be recorded and uploaded to Bytecode Alliance [YouTube channel](https://www.youtube.com/@bytecodealliance) in a playlist for the SIG. (Note: check "No it is not made for kids" when uploaded.)
- Meeting notes must be publicly available and easy to find, ideally by including them in the SIG's subfolder in the [`meetings`](https://github.com/bytecodealliance/meetings) repo or, if elsewhere, directly linked to from within that subfolder.
- Conversations about meetings should take place in the SIG's stream on Zulip, including discussion of agenda topics, proposals to move/cancel a meeting, or important changes in meeting logistics.